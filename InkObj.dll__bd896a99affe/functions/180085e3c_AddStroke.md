# AddStroke

- ea: `0x180085e3c`
- end: `0x18008614c`
- name: `AddStroke`
- size: `784`
- prototype: `HRESULT __stdcall(HRECOCONTEXT hrc, const PACKET_DESCRIPTION *pPacketDesc, ULONG cbPacket, const BYTE *pPacket, const XFORM *pXForm)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180069840`
- `0x1800a35d0`
- `0x1800c7bf0`
- `0x1800fbe74`

## callees

- `0x180044ac6`
- `0x180083dc0`
- `0x180085e3c`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085ede`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085ef9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085f2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085fa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180086014`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008606d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085ede`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085ef9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085f2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085fa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180086014`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008606d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085f6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085f75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085fee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086031`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086098`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800860ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800860b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800860c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800860fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008610d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086138`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086141`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085f6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085f75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085fee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086031`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086098`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800860ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800860b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800860c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800860fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008610d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086138`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086141`

## pseudocode

```c
HRESULT __stdcall AddStroke(
        HRECOCONTEXT hrc,
        const PACKET_DESCRIPTION *pPacketDesc,
        ULONG cbPacket,
        const BYTE *pPacket,
        const XFORM *pXForm)
{
  SIZE_T v5; // rbp
  HRESULT v9; // edi
  LPVOID *v11; // rax
  LPVOID *v12; // rbx
  void *v13; // rax
  _DWORD *v14; // rax
  void *v15; // rcx
  __int64 cPacketProperties; // rcx
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  __int64 cButtons; // rcx
  void *v21; // rcx
  XFORM *v22; // rax
  LPVOID *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  LPVOID *v26; // rcx

  v5 = cbPacket;
  if ( !hrc )
    return -2147467261;
  if ( *((_QWORD *)hrc + 2) )
  {
    if ( pPacketDesc
      && (pPacketDesc->cPacketProperties && !pPacketDesc->pPacketProperties
       || pPacketDesc->cButtons && !pPacketDesc->pguidButtons) )
    {
      return -2147467261;
    }
    if ( !cbPacket )
      return -2147024809;
    if ( !pPacket )
      return -2147467261;
    *((_QWORD *)hrc + 12) = 1;
    *((_QWORD *)hrc + 13) = 0;
    v11 = (LPVOID *)CoTaskMemAlloc(0x20u);
    v12 = v11;
    if ( !v11 )
      return -2147024882;
    *((_DWORD *)v11 + 2) = v5;
    v13 = CoTaskMemAlloc(v5);
    v12[2] = v13;
    if ( !v13 )
      goto LABEL_48;
    memcpy_0(v13, pPacket, v5);
    *v12 = 0;
    if ( pPacketDesc )
    {
      v14 = CoTaskMemAlloc(0x20u);
      *v12 = v14;
      if ( !v14 )
      {
        v15 = v12[2];
LABEL_47:
        CoTaskMemFree(v15);
        goto LABEL_48;
      }
      *v14 = pPacketDesc->cbPacketSize;
      *((_DWORD *)*v12 + 1) = pPacketDesc->cPacketProperties;
      *((_QWORD *)*v12 + 1) = 0;
      cPacketProperties = pPacketDesc->cPacketProperties;
      if ( (_DWORD)cPacketProperties )
      {
        if ( (unsigned int)cPacketProperties >= 0x3FFFFFF )
        {
          v17 = v12[2];
          goto LABEL_22;
        }
        if ( 32 * (_DWORD)cPacketProperties && !pPacketDesc->pPacketProperties
          || (*((_QWORD *)*v12 + 1) = CoTaskMemAlloc(32 * cPacketProperties), (v19 = (void *)*((_QWORD *)*v12 + 1)) == 0) )
        {
          v18 = v12[2];
          goto LABEL_45;
        }
        memcpy_0(v19, pPacketDesc->pPacketProperties, 32LL * pPacketDesc->cPacketProperties);
      }
      *((_QWORD *)*v12 + 3) = 0;
      *((_DWORD *)*v12 + 4) = pPacketDesc->cButtons;
      cButtons = pPacketDesc->cButtons;
      if ( (_DWORD)cButtons )
      {
        if ( (unsigned int)cButtons >= 0x7FFFFFF )
        {
          CoTaskMemFree(v12[2]);
          if ( !*((_DWORD *)*v12 + 1) )
            goto LABEL_23;
          v17 = (void *)*((_QWORD *)*v12 + 1);
LABEL_22:
          CoTaskMemFree(v17);
LABEL_23:
          CoTaskMemFree(*v12);
          v9 = -2147418113;
LABEL_49:
          CoTaskMemFree(v12);
          return v9;
        }
        if ( !pPacketDesc->pguidButtons
          || (*((_QWORD *)*v12 + 3) = CoTaskMemAlloc(16 * cButtons), (v21 = (void *)*((_QWORD *)*v12 + 3)) == 0) )
        {
          CoTaskMemFree(v12[2]);
          if ( !*((_DWORD *)*v12 + 1) )
          {
LABEL_46:
            v15 = *v12;
            goto LABEL_47;
          }
          v18 = (void *)*((_QWORD *)*v12 + 1);
LABEL_45:
          CoTaskMemFree(v18);
          goto LABEL_46;
        }
        memcpy_0(v21, pPacketDesc->pguidButtons, 16LL * pPacketDesc->cButtons);
      }
    }
    v12[3] = 0;
    if ( pXForm )
    {
      v22 = (XFORM *)CoTaskMemAlloc(0x18u);
      v12[3] = v22;
      if ( !v22 )
      {
        CoTaskMemFree(v12[2]);
        v23 = (LPVOID *)*v12;
        if ( !*v12 )
        {
LABEL_48:
          v9 = -2147024882;
          goto LABEL_49;
        }
        if ( *((_DWORD *)v23 + 1) )
          CoTaskMemFree(v23[1]);
        if ( !*((_DWORD *)*v12 + 4) )
          goto LABEL_46;
        v18 = (void *)*((_QWORD *)*v12 + 3);
        goto LABEL_45;
      }
      *v22 = *pXForm;
    }
    v9 = AddToQueue(hrc, 1, v12);
    if ( v9 >= 0 )
      return v9;
    v24 = v12[3];
    if ( v24 )
      CoTaskMemFree(v24);
    v25 = v12[2];
    if ( v25 )
      CoTaskMemFree(v25);
    v26 = (LPVOID *)*v12;
    if ( *v12 )
    {
      if ( *((_DWORD *)v26 + 1) )
        CoTaskMemFree(v26[1]);
      if ( *((_DWORD *)*v12 + 4) )
        CoTaskMemFree(*((LPVOID *)*v12 + 3));
      CoTaskMemFree(*v12);
    }
    goto LABEL_49;
  }
  return (*(__int64 (__fastcall **)(_QWORD, const PACKET_DESCRIPTION *, _QWORD, const BYTE *, const XFORM *))(*(_QWORD *)hrc + 64LL))(
           *((_QWORD *)hrc + 1),
           pPacketDesc,
           cbPacket,
           pPacket,
           pXForm);
}

```

## disassembly

```asm
0x180085e3c  push    rbx
0x180085e3e  push    rbp
0x180085e3f  push    rsi
0x180085e40  push    rdi
0x180085e41  push    r14
0x180085e43  push    r15
0x180085e45  sub     rsp, 38h
0x180085e49  xor     r15d, r15d
0x180085e4c  mov     ebp, r8d
0x180085e4f  mov     r14, r9
0x180085e52  mov     rdi, rdx
0x180085e55  mov     rsi, rcx
0x180085e58  test    rcx, rcx
0x180085e5b  jz      short loc_180085EB4
0x180085e5d  cmp     [rcx+10h], r15
0x180085e61  jnz     short loc_180085E8D
0x180085e63  mov     rax, [rcx]
0x180085e66  mov     r8d, ebp
0x180085e69  mov     r9, [rsp+68h+pXForm]
0x180085e71  mov     rcx, [rcx+8]
0x180085e75  mov     [rsp+68h+var_48], r9
0x180085e7a  mov     r9, r14
0x180085e7d  mov     rax, [rax+40h]
0x180085e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085e86  mov     edi, eax
0x180085e88  jmp     loc_1800860C8
0x180085e8d  test    rdi, rdi
0x180085e90  jz      short loc_180085EAA
0x180085e92  cmp     [rdx+4], r15d
0x180085e96  jz      short loc_180085E9E
0x180085e98  cmp     [rdx+8], r15
0x180085e9c  jz      short loc_180085EB4
0x180085e9e  cmp     [rdx+10h], r15d
0x180085ea2  jz      short loc_180085EAA
0x180085ea4  cmp     [rdx+18h], r15
0x180085ea8  jz      short loc_180085EB4
0x180085eaa  test    r8d, r8d
0x180085ead  jz      short loc_180085EC6
0x180085eaf  test    r14, r14
0x180085eb2  jnz     short loc_180085ECD
0x180085eb4  mov     eax, 80004003h
0x180085eb9  add     rsp, 38h
0x180085ebd  pop     r15
0x180085ebf  pop     r14
0x180085ec1  pop     rdi
0x180085ec2  pop     rsi
0x180085ec3  pop     rbp
0x180085ec4  pop     rbx
0x180085ec5  retn
0x180085ec6  mov     eax, 80070057h
0x180085ecb  jmp     short loc_180085EB9
0x180085ecd  mov     qword ptr [rcx+60h], 1
0x180085ed5  mov     [rcx+68h], r15
0x180085ed9  mov     ecx, 20h ; ' '; cb
0x180085ede  call    cs:__imp_CoTaskMemAlloc
0x180085ee4  mov     rbx, rax
0x180085ee7  test    rax, rax
0x180085eea  jnz     short loc_180085EF3
0x180085eec  mov     eax, 8007000Eh
0x180085ef1  jmp     short loc_180085EB9
0x180085ef3  mov     rcx, rbp; cb
0x180085ef6  mov     [rax+8], ebp
0x180085ef9  call    cs:__imp_CoTaskMemAlloc
0x180085eff  mov     [rbx+10h], rax
0x180085f03  test    rax, rax
0x180085f06  jz      loc_1800860BA
0x180085f0c  mov     r8, rbp; Size
0x180085f0f  mov     rdx, r14; Src
0x180085f12  mov     rcx, rax; void *
0x180085f15  call    memcpy_0
0x180085f1a  mov     [rbx], r15
0x180085f1d  test    rdi, rdi
0x180085f20  jz      loc_180086057
0x180085f26  mov     ecx, 20h ; ' '; cb
0x180085f2b  call    cs:__imp_CoTaskMemAlloc
0x180085f31  mov     [rbx], rax
0x180085f34  mov     rcx, rax
0x180085f37  test    rax, rax
0x180085f3a  jnz     short loc_180085F45
0x180085f3c  mov     rcx, [rbx+10h]
0x180085f40  jmp     loc_1800860B4
0x180085f45  mov     eax, [rdi]
0x180085f47  mov     [rcx], eax
0x180085f49  mov     rcx, [rbx]
0x180085f4c  mov     eax, [rdi+4]
0x180085f4f  mov     [rcx+4], eax
0x180085f52  mov     rax, [rbx]
0x180085f55  mov     [rax+8], r15
0x180085f59  mov     ecx, [rdi+4]
0x180085f5c  test    ecx, ecx
0x180085f5e  jz      short loc_180085FCB
0x180085f60  cmp     ecx, 3FFFFFFh
0x180085f66  jb      short loc_180085F85
0x180085f68  mov     rcx, [rbx+10h]; pv
0x180085f6c  call    cs:__imp_CoTaskMemFree
0x180085f72  mov     rcx, [rbx]; pv
0x180085f75  call    cs:__imp_CoTaskMemFree
0x180085f7b  mov     edi, 8000FFFFh
0x180085f80  jmp     loc_1800860BF
0x180085f85  mov     eax, ecx
0x180085f87  shl     eax, 5
0x180085f8a  test    eax, eax
0x180085f8c  jz      short loc_180085F9D
0x180085f8e  cmp     [rdi+8], r15
0x180085f92  jnz     short loc_180085F9D
0x180085f94  mov     rcx, [rbx+10h]
0x180085f98  jmp     loc_1800860AB
0x180085f9d  shl     rcx, 5; cb
0x180085fa1  call    cs:__imp_CoTaskMemAlloc
0x180085fa7  mov     rcx, [rbx]
0x180085faa  mov     [rcx+8], rax
0x180085fae  mov     rax, [rbx]
0x180085fb1  mov     rcx, [rax+8]; void *
0x180085fb5  test    rcx, rcx
0x180085fb8  jz      short loc_180085F94
0x180085fba  mov     r8d, [rdi+4]
0x180085fbe  mov     rdx, [rdi+8]; Src
0x180085fc2  shl     r8, 5; Size
0x180085fc6  call    memcpy_0
0x180085fcb  mov     rax, [rbx]
0x180085fce  mov     [rax+18h], r15
0x180085fd2  mov     rcx, [rbx]
0x180085fd5  mov     eax, [rdi+10h]
0x180085fd8  mov     [rcx+10h], eax
0x180085fdb  mov     ecx, [rdi+10h]
0x180085fde  test    ecx, ecx
0x180085fe0  jz      short loc_180086057
0x180085fe2  cmp     ecx, 7FFFFFFh
0x180085fe8  jb      short loc_18008600A
0x180085fea  mov     rcx, [rbx+10h]; pv
0x180085fee  call    cs:__imp_CoTaskMemFree
0x180085ff4  mov     rcx, [rbx]
0x180085ff7  cmp     [rcx+4], r15d
0x180085ffb  jz      loc_180085F72
0x180086001  mov     rcx, [rcx+8]
0x180086005  jmp     loc_180085F6C
0x18008600a  cmp     [rdi+18h], r15
0x18008600e  jz      short loc_18008602D
0x180086010  shl     rcx, 4; cb
0x180086014  call    cs:__imp_CoTaskMemAlloc
0x18008601a  mov     rcx, [rbx]
0x18008601d  mov     [rcx+18h], rax
0x180086021  mov     rax, [rbx]
0x180086024  mov     rcx, [rax+18h]; void *
0x180086028  test    rcx, rcx
0x18008602b  jnz     short loc_180086046
0x18008602d  mov     rcx, [rbx+10h]; pv
0x180086031  call    cs:__imp_CoTaskMemFree
0x180086037  mov     rcx, [rbx]
0x18008603a  cmp     [rcx+4], r15d
0x18008603e  jz      short loc_1800860B1
0x180086040  mov     rcx, [rcx+8]
0x180086044  jmp     short loc_1800860AB
0x180086046  mov     r8d, [rdi+10h]
0x18008604a  mov     rdx, [rdi+18h]; Src
0x18008604e  shl     r8, 4; Size
0x180086052  call    memcpy_0
0x180086057  mov     rdi, [rsp+68h+pXForm]
0x18008605f  mov     [rbx+18h], r15
0x180086063  test    rdi, rdi
0x180086066  jz      short loc_1800860DF
0x180086068  mov     ecx, 18h; cb
0x18008606d  call    cs:__imp_CoTaskMemAlloc
0x180086073  mov     [rbx+18h], rax
0x180086077  test    rax, rax
0x18008607a  jnz     short loc_1800860CF
0x18008607c  mov     rcx, [rbx+10h]; pv
0x180086080  call    cs:__imp_CoTaskMemFree
0x180086086  mov     rcx, [rbx]
0x180086089  test    rcx, rcx
0x18008608c  jz      short loc_1800860BA
0x18008608e  cmp     [rcx+4], r15d
0x180086092  jz      short loc_18008609E
0x180086094  mov     rcx, [rcx+8]; pv
0x180086098  call    cs:__imp_CoTaskMemFree
0x18008609e  mov     rcx, [rbx]
0x1800860a1  cmp     [rcx+10h], r15d
0x1800860a5  jz      short loc_1800860B1
0x1800860a7  mov     rcx, [rcx+18h]; pv
0x1800860ab  call    cs:__imp_CoTaskMemFree
0x1800860b1  mov     rcx, [rbx]; pv
0x1800860b4  call    cs:__imp_CoTaskMemFree
0x1800860ba  mov     edi, 8007000Eh
0x1800860bf  mov     rcx, rbx; pv
0x1800860c2  call    cs:__imp_CoTaskMemFree
0x1800860c8  mov     eax, edi
0x1800860ca  jmp     loc_180085EB9
0x1800860cf  movups  xmm0, xmmword ptr [rdi]
0x1800860d2  movups  xmmword ptr [rax], xmm0
0x1800860d5  movsd   xmm1, qword ptr [rdi+10h]
0x1800860da  movsd   qword ptr [rax+10h], xmm1
0x1800860df  mov     r8, rbx
0x1800860e2  mov     edx, 1
0x1800860e7  mov     rcx, rsi
0x1800860ea  call    ?AddToQueue@@YAJPEAUtagWispContext@@W4OpType@@PEAX@Z; AddToQueue(tagWispContext *,OpType,void *)
0x1800860ef  mov     edi, eax
0x1800860f1  test    eax, eax
0x1800860f3  jns     short loc_1800860C8
0x1800860f5  mov     rcx, [rbx+18h]; pv
0x1800860f9  test    rcx, rcx
0x1800860fc  jz      short loc_180086104
0x1800860fe  call    cs:__imp_CoTaskMemFree
0x180086104  mov     rcx, [rbx+10h]; pv
0x180086108  test    rcx, rcx
0x18008610b  jz      short loc_180086113
0x18008610d  call    cs:__imp_CoTaskMemFree
0x180086113  mov     rcx, [rbx]
0x180086116  test    rcx, rcx
0x180086119  jz      short loc_1800860BF
0x18008611b  cmp     [rcx+4], r15d
0x18008611f  jz      short loc_18008612B
0x180086121  mov     rcx, [rcx+8]; pv
0x180086125  call    cs:__imp_CoTaskMemFree
0x18008612b  mov     rcx, [rbx]
0x18008612e  cmp     [rcx+10h], r15d
0x180086132  jz      short loc_18008613E
0x180086134  mov     rcx, [rcx+18h]; pv
0x180086138  call    cs:__imp_CoTaskMemFree
0x18008613e  mov     rcx, [rbx]; pv
0x180086141  call    cs:__imp_CoTaskMemFree
0x180086147  jmp     loc_1800860BF
```
