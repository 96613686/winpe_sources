# ASFCreateMediaObjectIndexMaker

- ea: `0x180032b00`
- end: `0x180032bcd`
- name: `ASFCreateMediaObjectIndexMaker`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001174`
- `0x180032b00`
- `0x18003cec4`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall ASFCreateMediaObjectIndexMaker(struct IASFLibrary *a1, struct IASFIndexMakerSink *a2, __int64 a3)
{
  CASFBaseIndexMaker *v7; // rax
  CASFBaseIndexMaker *v8; // rbx
  int v9; // esi

  if ( !a3 )
    return 2147942487LL;
  v7 = (CASFBaseIndexMaker *)operator new(0x32D8u);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  CASFBaseIndexMaker::CASFBaseIndexMaker(v7);
  *((_DWORD *)v8 + 17) = 1000;
  *(_QWORD *)v8 = &CASFFrameIndexMaker::`vftable'{for `IASFIndexMaker'};
  *((_QWORD *)v8 + 1) = &CASFBaseIndexMaker::`vftable'{for `IASFReadWriteTracker'};
  *((_DWORD *)v8 + 16) = 30;
  *((GUID *)v8 + 2) = CLSID_ASFMediaObjectIndexParametersObject;
  *((GUID *)v8 + 3) = CLSID_ASFMediaObjectIndexObject;
  v9 = CASFBaseIndexMaker::Init(v8, a1, a2);
  if ( v9 >= 0 )
    v9 = (**(__int64 (__fastcall ***)(CASFBaseIndexMaker *, GUID *, __int64))v8)(v8, &IID_IASFIndexMaker, a3);
  (*(void (__fastcall **)(CASFBaseIndexMaker *))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180032b00  push    rbx
0x180032b02  push    rbp
0x180032b03  push    rsi
0x180032b04  push    rdi
0x180032b05  sub     rsp, 28h
0x180032b09  mov     rdi, r8
0x180032b0c  mov     rsi, rdx
0x180032b0f  mov     rbp, rcx
0x180032b12  test    r8, r8
0x180032b15  jnz     short loc_180032B21
0x180032b17  mov     eax, 80070057h
0x180032b1c  jmp     loc_180032BC4
0x180032b21  mov     ecx, 32D8h; Size
0x180032b26  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032b2b  mov     rbx, rax
0x180032b2e  test    rax, rax
0x180032b31  jz      loc_180032BBF
0x180032b37  mov     rcx, rax; this
0x180032b3a  call    ??0CASFBaseIndexMaker@@QEAA@XZ; CASFBaseIndexMaker::CASFBaseIndexMaker(void)
0x180032b3f  lea     r9, ??_7CASFFrameIndexMaker@@6BIASFIndexMaker@@@; const CASFFrameIndexMaker::`vftable'{for `IASFIndexMaker'}
0x180032b46  mov     dword ptr [rbx+44h], 3E8h
0x180032b4d  mov     [rbx], r9
0x180032b50  lea     rax, ??_7CASFBaseIndexMaker@@6BIASFReadWriteTracker@@@; const CASFBaseIndexMaker::`vftable'{for `IASFReadWriteTracker'}
0x180032b57  mov     [rbx+8], rax
0x180032b5b  mov     r8, rsi
0x180032b5e  mov     rax, [r9+18h]
0x180032b62  mov     rdx, rbp
0x180032b65  mov     dword ptr [rbx+40h], 1Eh
0x180032b6c  mov     rcx, rbx
0x180032b6f  movups  xmm0, xmmword ptr cs:CLSID_ASFMediaObjectIndexParametersObject.Data1
0x180032b76  movdqu  xmmword ptr [rbx+20h], xmm0
0x180032b7b  movups  xmm1, xmmword ptr cs:CLSID_ASFMediaObjectIndexObject.Data1
0x180032b82  movdqu  xmmword ptr [rbx+30h], xmm1
0x180032b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b8c  mov     esi, eax
0x180032b8e  test    eax, eax
0x180032b90  js      short loc_180032BAC
0x180032b92  mov     rax, [rbx]
0x180032b95  lea     rdx, IID_IASFIndexMaker
0x180032b9c  mov     r8, rdi
0x180032b9f  mov     rcx, rbx
0x180032ba2  mov     rax, [rax]
0x180032ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032baa  mov     esi, eax
0x180032bac  mov     rax, [rbx]
0x180032baf  mov     rcx, rbx
0x180032bb2  mov     rax, [rax+10h]
0x180032bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bbb  mov     eax, esi
0x180032bbd  jmp     short loc_180032BC4
0x180032bbf  mov     eax, 8007000Eh
0x180032bc4  add     rsp, 28h
0x180032bc8  pop     rdi
0x180032bc9  pop     rsi
0x180032bca  pop     rbp
0x180032bcb  pop     rbx
0x180032bcc  retn
```
