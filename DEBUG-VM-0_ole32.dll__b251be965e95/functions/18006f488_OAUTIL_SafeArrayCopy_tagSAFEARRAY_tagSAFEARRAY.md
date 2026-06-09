# OAUTIL::SafeArrayCopy(tagSAFEARRAY *,tagSAFEARRAY * *)

- ea: `0x18006f488`
- end: `0x18006f61b`
- name: `?SafeArrayCopy@OAUTIL@@QEAAJPEAUtagSAFEARRAY@@PEAPEAU2@@Z`
- size: `403`
- prototype: `HRESULT __fastcall(OAUTIL *this, tagSAFEARRAY *psa, tagSAFEARRAY **ppsaOut)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18006fc30`
- `0x18007088c`
- `0x180071f7c`

## callees

- `0x18006f488`
- `0x18006f624`
- `0x18006f924`
- `0x1800c4651`
- `0x1800ce010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAllocDescriptor` at `0x18006f565`
- `OLEAUT32!__imp_SafeArrayAllocDescriptor` at `0x18006f565`
- `OLEAUT32!__imp_SafeArrayAllocData` at `0x18006f5c5`
- `OLEAUT32!__imp_SafeArrayAllocData` at `0x18006f5c5`
- `OLEAUT32!__imp_SafeArrayAllocDescriptorEx` at `0x18006f4e5`
- `OLEAUT32!__imp_SafeArrayAllocDescriptorEx` at `0x18006f528`
- `OLEAUT32!__imp_SafeArrayAllocDescriptorEx` at `0x18006f556`
- `OLEAUT32!__imp_SafeArrayAllocDescriptorEx` at `0x18006f4e5`
- `OLEAUT32!__imp_SafeArrayAllocDescriptorEx` at `0x18006f528`
- `OLEAUT32!__imp_SafeArrayAllocDescriptorEx` at `0x18006f556`

## pseudocode

```c
__int64 __fastcall OAUTIL::SafeArrayCopy(OAUTIL *this, tagSAFEARRAY *psa, tagSAFEARRAY **ppsaOut)
{
  unsigned int v6; // ebx
  unsigned __int16 fFeatures; // ax
  tagSAFEARRAYBOUND v8; // rcx
  HRESULT v9; // eax
  tagSAFEARRAY *v10; // rdx
  tagSAFEARRAY *psaNew; // [rsp+50h] [rbp+30h] BYREF

  psaNew = 0;
  if ( !ppsaOut )
    return (unsigned int)-2147024809;
  v6 = 0;
  *ppsaOut = 0;
  if ( !psa )
    return v6;
  fFeatures = psa->fFeatures;
  if ( (fFeatures & 0xE0) == 0 )
  {
    v9 = SafeArrayAllocDescriptor(psa->cDims, &psaNew);
LABEL_15:
    v6 = v9;
    if ( v9 )
      goto LABEL_19;
    goto LABEL_16;
  }
  if ( (fFeatures & 0x20) != 0 )
  {
    v6 = SafeArrayAllocDescriptorEx(0x24u, psa->cDims, &psaNew);
    if ( v6 )
      goto LABEL_19;
    psaNew[-1].rgsabound[0] = psa[-1].rgsabound[0];
    v8 = psa[-1].rgsabound[0];
    if ( v8 )
      (*(void (__fastcall **)(tagSAFEARRAYBOUND))(**(_QWORD **)&v8 + 8LL))(v8);
    goto LABEL_16;
  }
  if ( (fFeatures & 0x40) != 0 )
  {
    v6 = SafeArrayAllocDescriptorEx(0xDu, psa->cDims, &psaNew);
    if ( v6 )
      goto LABEL_19;
    *(_OWORD *)&psaNew[-1].pvData = *(_OWORD *)&psa[-1].pvData;
    goto LABEL_16;
  }
  if ( (fFeatures & 0x80u) != 0 )
  {
    v9 = SafeArrayAllocDescriptorEx(psa[-1].rgsabound[0].lLbound, psa->cDims, &psaNew);
    goto LABEL_15;
  }
LABEL_16:
  psaNew->cLocks = 0;
  psaNew->cDims = psa->cDims;
  psaNew->fFeatures = psa->fFeatures & 0xEFE8;
  psaNew->cbElements = psa->cbElements;
  memcpy_0(psaNew->rgsabound, psa->rgsabound, 8LL * psa->cDims);
  v6 = SafeArrayAllocData(psaNew);
  if ( !v6 )
  {
    v6 = OAUTIL::SafeArrayCopyData(this, psa, psaNew);
    if ( !v6 )
    {
      v10 = 0;
      *ppsaOut = psaNew;
      psaNew = 0;
      goto LABEL_20;
    }
  }
LABEL_19:
  v10 = psaNew;
LABEL_20:
  if ( v10 )
    OAUTIL::SafeArrayDestroy(this, v10);
  return v6;
}

```

## disassembly

```asm
0x18006f488  mov     [rsp-18h+arg_0], rbx
0x18006f48d  mov     [rsp-18h+arg_8], rsi
0x18006f492  push    rbp
0x18006f493  push    rdi
0x18006f494  push    r14
0x18006f496  mov     rbp, rsp
0x18006f499  sub     rsp, 20h
0x18006f49d  mov     [rbp+psaNew], 0
0x18006f4a5  mov     rsi, ppsaOut
0x18006f4a8  mov     rdi, psa
0x18006f4ab  mov     r14, this
0x18006f4ae  test    ppsaOut, ppsaOut
0x18006f4b1  jnz     short loc_18006F4BD
0x18006f4b3  mov     ebx, 80070057h
0x18006f4b8  jmp     loc_18006F606
0x18006f4bd  xor     ebx, ebx
0x18006f4bf  mov     [ppsaOut], rbx
0x18006f4c2  test    rdi, rdi
0x18006f4c5  jz      loc_18006F606
0x18006f4cb  movzx   eax, word ptr [psa+2]
0x18006f4cf  test    al, 0E0h
0x18006f4d1  jz      loc_18006F55E
0x18006f4d7  test    al, 20h
0x18006f4d9  jz      short loc_18006F518
0x18006f4db  movzx   edx, word ptr [psa]; cDims
0x18006f4de  lea     ecx, [rbx+24h]; vt
0x18006f4e1  lea     ppsaOut, [rbp+psaNew]; ppsaOut
0x18006f4e5  call    cs:__imp_SafeArrayAllocDescriptorEx
0x18006f4eb  mov     ebx, eax
0x18006f4ed  test    eax, eax
0x18006f4ef  jnz     loc_18006F5F5
0x18006f4f5  mov     this, [rdi-8]
0x18006f4f9  mov     rax, [rbp+psaNew]
0x18006f4fd  mov     [rax-8], this
0x18006f501  mov     this, [rdi-8]
0x18006f505  test    this, this
0x18006f508  jz      short loc_18006F575
0x18006f50a  mov     rax, [this]
0x18006f50d  mov     rax, [rax+8]
0x18006f511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f516  jmp     short loc_18006F575
0x18006f518  test    al, 40h
0x18006f51a  jz      short loc_18006F547
0x18006f51c  movzx   edx, word ptr [psa]; cDims
0x18006f51f  lea     ppsaOut, [rbp+psaNew]; ppsaOut
0x18006f523  mov     ecx, 0Dh; vt
0x18006f528  call    cs:__imp_SafeArrayAllocDescriptorEx
0x18006f52e  mov     ebx, eax
0x18006f530  test    eax, eax
0x18006f532  jnz     loc_18006F5F5
0x18006f538  mov     rax, [rbp+psaNew]
0x18006f53c  movups  xmm0, xmmword ptr [rdi-10h]
0x18006f540  movdqu  xmmword ptr [rax-10h], xmm0
0x18006f545  jmp     short loc_18006F575
0x18006f547  test    al, al
0x18006f549  jns     short loc_18006F575
0x18006f54b  movzx   edx, word ptr [psa]; cDims
0x18006f54e  lea     ppsaOut, [rbp+psaNew]; ppsaOut
0x18006f552  movzx   ecx, word ptr [rdi-4]; vt
0x18006f556  call    cs:__imp_SafeArrayAllocDescriptorEx
0x18006f55c  jmp     short loc_18006F56B
0x18006f55e  movzx   ecx, word ptr [psa]; cDims
0x18006f561  lea     psa, [rbp+psaNew]; ppsaOut
0x18006f565  call    cs:__imp_SafeArrayAllocDescriptor
0x18006f56b  mov     ebx, eax
0x18006f56d  test    eax, eax
0x18006f56f  jnz     loc_18006F5F5
0x18006f575  mov     rax, [rbp+psaNew]
0x18006f579  lea     psa, [rdi+18h]; Src
0x18006f57d  mov     dword ptr [rax+8], 0
0x18006f584  movzx   ecx, word ptr [rdi]
0x18006f587  mov     rax, [rbp+psaNew]
0x18006f58b  mov     [rax], cx
0x18006f58e  mov     eax, 0EFE8h
0x18006f593  movzx   ecx, word ptr [rdi+2]
0x18006f597  and     cx, ax
0x18006f59a  mov     rax, [rbp+psaNew]
0x18006f59e  mov     [rax+2], cx
0x18006f5a2  mov     ecx, [rdi+4]
0x18006f5a5  mov     rax, [rbp+psaNew]
0x18006f5a9  mov     [rax+4], ecx
0x18006f5ac  movzx   r8d, word ptr [rdi]
0x18006f5b0  mov     this, [rbp+psaNew]
0x18006f5b4  shl     ppsaOut, 3; Size
0x18006f5b8  add     this, 18h; void *
0x18006f5bc  call    memcpy_0
0x18006f5c1  mov     this, [rbp+psaNew]; psa
0x18006f5c5  call    cs:__imp_SafeArrayAllocData
0x18006f5cb  mov     ebx, eax
0x18006f5cd  test    eax, eax
0x18006f5cf  jnz     short loc_18006F5F5
0x18006f5d1  mov     ppsaOut, [rbp+psaNew]; psaTarget
0x18006f5d5  mov     psa, rdi; psaSource
0x18006f5d8  mov     this, r14; this
0x18006f5db  call    ?SafeArrayCopyData@OAUTIL@@QEAAJPEAUtagSAFEARRAY@@0@Z; OAUTIL::SafeArrayCopyData(tagSAFEARRAY *,tagSAFEARRAY *)
0x18006f5e0  mov     ebx, eax
0x18006f5e2  test    eax, eax
0x18006f5e4  jnz     short loc_18006F5F5
0x18006f5e6  mov     rax, [rbp+psaNew]
0x18006f5ea  xor     edx, edx
0x18006f5ec  mov     [rsi], rax
0x18006f5ef  mov     [rbp+psaNew], psa
0x18006f5f3  jmp     short loc_18006F5F9
0x18006f5f5  mov     psa, [rbp+psaNew]; psa
0x18006f5f9  test    psa, psa
0x18006f5fc  jz      short loc_18006F606
0x18006f5fe  mov     this, r14; this
0x18006f601  call    ?SafeArrayDestroy@OAUTIL@@QEAAJPEAUtagSAFEARRAY@@@Z; OAUTIL::SafeArrayDestroy(tagSAFEARRAY *)
0x18006f606  mov     rsi, [rsp+20h+arg_8]
0x18006f60b  mov     eax, ebx
0x18006f60d  mov     rbx, [rsp+20h+arg_0]
0x18006f612  add     rsp, 20h
0x18006f616  pop     r14
0x18006f618  pop     rdi
0x18006f619  pop     rbp
0x18006f61a  retn
```
