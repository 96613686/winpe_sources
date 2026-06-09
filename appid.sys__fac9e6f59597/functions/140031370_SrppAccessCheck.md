# SrppAccessCheck

- ea: `0x140031370`
- end: `0x1400315a1`
- name: `SrppAccessCheck`
- size: `561`
- prototype: `__int64 __fastcall(HANDLE, __int64, const UNICODE_STRING *, char, char, _DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140030ff0`
- `0x140034550`

## callees

- `0x140006a20`
- `0x140006f40`
- `0x140031370`
- `0x140031890`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003141a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003141a`
- `ntoskrnl!ObfDereferenceObject` at `0x14003152b`
- `ntoskrnl!ObfDereferenceObject` at `0x14003152b`
- `ntoskrnl!SeSrpAccessCheck` at `0x1400314f5`
- `ntoskrnl!SeSrpAccessCheck` at `0x1400314f5`

## pseudocode

```c
__int64 __fastcall SrppAccessCheck(HANDLE a1, __int64 a2, const UNICODE_STRING *a3, char a4, char a5, _DWORD *a6)
{
  __int64 v10; // r13
  NTSTATUS v11; // eax
  PVOID v12; // rbx
  unsigned int v13; // ebx
  int HandleInformation; // [rsp+28h] [rbp-D8h]
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+44h] [rbp-BCh] BYREF
  PVOID Object; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v19; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v20; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v21; // [rsp+70h] [rbp-90h]
  __int64 v22; // [rsp+80h] [rbp-80h]
  __int128 v23; // [rsp+88h] [rbp-78h] BYREF
  __int128 v24; // [rsp+98h] [rbp-68h]
  _BYTE v25[24]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v26; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v27; // [rsp+D0h] [rbp-30h]
  _DWORD v28[32]; // [rsp+E0h] [rbp-20h] BYREF

  memset(v28, 0, sizeof(v28));
  v10 = *(_QWORD *)(a2 + 40);
  v22 = 0;
  v17 = 0;
  Object = 0;
  v26 = 0;
  v27 = 0;
  v19 = 0;
  v23 = 0;
  v24 = 0;
  memset(v25, 0, 20);
  v20 = 0;
  v21 = 0;
  v11 = ObReferenceObjectByHandle(a1, 0, 0, 0, &Object, 0);
  v12 = Object;
  v16 = v11;
  if ( v11 >= 0 )
  {
    LOBYTE(HandleInformation) = 1;
    *((_QWORD *)&v19 + 1) = v10 + *(unsigned int *)(v10 + 16);
    v26 = 0u;
    *(_QWORD *)v25 = qword_14000C000;
    *((_QWORD *)&v23 + 1) = &v19;
    *((_QWORD *)&v20 + 1) = &v17;
    v27 = (unsigned __int64)Object;
    *(_QWORD *)&v21 = &v16;
    *((_QWORD *)&v21 + 1) = v28;
    *(_QWORD *)&v19 = 0x300000010LL;
    *(_QWORD *)&v23 = 56;
    *(_OWORD *)&v25[8] = 0;
    v24 = 0x20u;
    *(_QWORD *)&v20 = 0x100000028LL;
    v22 = 0;
    if ( !(unsigned __int8)SeSrpAccessCheck(&v26, 0, &v23, &v20, 0, HandleInformation) && v16 == -1073741790 )
      v16 = (*(_BYTE *)(v10 + 24) & 1) != 0 ? 0xC0000364 : 0;
  }
  if ( v12 )
    ObfDereferenceObject(v12);
  v13 = v16;
  SrpDisplayAccessReason(qword_1400196F8, a3, a1, a4, a5);
  if ( a6 )
    *a6 = v28[5];
  return v13;
}

```

## disassembly

```asm
0x140031370  mov     [rsp-8+arg_18], rbx
0x140031375  push    rbp
0x140031376  push    rsi
0x140031377  push    rdi
0x140031378  push    r12
0x14003137a  push    r13
0x14003137c  push    r14
0x14003137e  push    r15
0x140031380  lea     rbp, [rsp-70h]
0x140031385  sub     rsp, 170h
0x14003138c  mov     rax, cs:__security_cookie
0x140031393  xor     rax, rsp
0x140031396  mov     [rbp+0A0h+var_40], rax
0x14003139a  mov     r14, [rbp+0A0h+arg_28]
0x1400313a1  mov     r12, r8
0x1400313a4  mov     rdi, rdx
0x1400313a7  mov     rsi, rcx
0x1400313aa  xor     edx, edx; Val
0x1400313ac  lea     rcx, [rbp+0A0h+var_C0]; void *
0x1400313b0  mov     r8d, 80h; Size
0x1400313b6  mov     r15d, r9d
0x1400313b9  call    memset
0x1400313be  mov     r13, [rdi+28h]
0x1400313c2  xorps   xmm0, xmm0
0x1400313c5  xor     ecx, ecx
0x1400313c7  xor     eax, eax
0x1400313c9  mov     [rsp+1A0h+HandleInformation], rcx; HandleInformation
0x1400313ce  xor     r9d, r9d; AccessMode
0x1400313d1  mov     [rbp+0A0h+var_E8], eax
0x1400313d4  xor     r8d, r8d; ObjectType
0x1400313d7  mov     [rbp+0A0h+var_120], rax
0x1400313db  xor     edx, edx; DesiredAccess
0x1400313dd  lea     rax, [rsp+1A0h+var_158]
0x1400313e2  mov     [rsp+1A0h+var_160], ecx
0x1400313e6  mov     [rsp+1A0h+var_15C], ecx
0x1400313ea  mov     [rsp+1A0h+var_158], rcx
0x1400313ef  mov     rcx, rsi; Handle
0x1400313f2  mov     [rsp+1A0h+Object], rax; Object
0x1400313f7  movups  [rbp+0A0h+var_E0], xmm0
0x1400313fb  movups  [rbp+0A0h+var_D0], xmm0
0x1400313ff  movups  [rsp+1A0h+var_150], xmm0
0x140031404  movups  [rbp+0A0h+var_118], xmm0
0x140031408  movups  [rbp+0A0h+var_108], xmm0
0x14003140c  movups  [rbp+0A0h+var_F8], xmm0
0x140031410  movups  [rsp+1A0h+var_140], xmm0
0x140031415  movups  [rsp+1A0h+var_130], xmm0
0x14003141a  call    cs:__imp_ObReferenceObjectByHandle
0x140031421  nop     dword ptr [rax+rax+00h]
0x140031426  mov     rbx, [rsp+1A0h+var_158]
0x14003142b  mov     [rsp+1A0h+var_160], eax
0x14003142f  test    eax, eax
0x140031431  js      loc_140031523
0x140031437  mov     eax, [r13+10h]
0x14003143b  lea     r9, [rsp+1A0h+var_140]
0x140031440  add     rax, r13
0x140031443  mov     byte ptr [rsp+1A0h+HandleInformation], 1
0x140031448  mov     qword ptr [rsp+1A0h+var_150+8], rax
0x14003144d  lea     r8, [rbp+0A0h+var_118]
0x140031451  lea     rax, qword_14000C000
0x140031458  mov     qword ptr [rbp+0A0h+var_E0], 0
0x140031460  mov     qword ptr [rbp+0A0h+var_F8], rax
0x140031464  lea     rcx, [rbp+0A0h+var_E0]
0x140031468  lea     rax, [rsp+1A0h+var_150]
0x14003146d  mov     qword ptr [rbp+0A0h+var_E0+8], 0
0x140031475  mov     qword ptr [rbp+0A0h+var_118+8], rax
0x140031479  xorps   xmm0, xmm0
0x14003147c  lea     rax, [rsp+1A0h+var_15C]
0x140031481  mov     qword ptr [rbp+0A0h+var_D0+8], 0
0x140031489  mov     qword ptr [rsp+1A0h+var_140+8], rax
0x14003148e  xor     edx, edx
0x140031490  lea     rax, [rsp+1A0h+var_160]
0x140031495  mov     qword ptr [rbp+0A0h+var_D0], rbx
0x140031499  mov     qword ptr [rsp+1A0h+var_130], rax
0x14003149e  lea     rax, [rbp+0A0h+var_C0]
0x1400314a2  mov     qword ptr [rsp+1A0h+var_130+8], rax
0x1400314a7  mov     dword ptr [rsp+1A0h+var_150], 10h
0x1400314af  mov     dword ptr [rsp+1A0h+var_150+4], 3
0x1400314b7  mov     qword ptr [rbp+0A0h+var_118], 38h ; '8'
0x1400314bf  mov     qword ptr [rbp+0A0h+var_108+8], 0
0x1400314c7  movdqu  [rbp+0A0h+var_F8+8], xmm0
0x1400314cc  mov     qword ptr [rbp+0A0h+var_108], 20h ; ' '
0x1400314d4  mov     dword ptr [rsp+1A0h+var_140], 28h ; '('
0x1400314dc  mov     dword ptr [rsp+1A0h+var_140+4], 1
0x1400314e4  mov     [rbp+0A0h+var_120], 0
0x1400314ec  mov     [rsp+1A0h+Object], 0
0x1400314f5  call    cs:__imp_SeSrpAccessCheck
0x1400314fc  nop     dword ptr [rax+rax+00h]
0x140031501  test    al, al
0x140031503  jnz     short loc_140031523
0x140031505  cmp     [rsp+1A0h+var_160], 0C0000022h
0x14003150d  jnz     short loc_140031523
0x14003150f  movzx   eax, byte ptr [r13+18h]
0x140031514  and     al, 1
0x140031516  neg     al
0x140031518  sbb     eax, eax
0x14003151a  and     eax, 0C0000364h
0x14003151f  mov     [rsp+1A0h+var_160], eax
0x140031523  test    rbx, rbx
0x140031526  jz      short loc_140031537
0x140031528  mov     rcx, rbx; Object
0x14003152b  call    cs:__imp_ObfDereferenceObject
0x140031532  nop     dword ptr [rax+rax+00h]
0x140031537  movzx   eax, [rbp+0A0h+arg_20]
0x14003153e  mov     r8, rdi
0x140031541  mov     r9d, [rbp+0A0h+var_AC]
0x140031545  mov     rdx, [rdi+28h]
0x140031549  mov     rcx, cs:qword_1400196F8; RegHandle
0x140031550  mov     ebx, [rsp+1A0h+var_160]
0x140031554  mov     [rsp+1A0h+var_168], al; char
0x140031558  mov     dword ptr [rsp+1A0h+var_170], r15d; char
0x14003155d  mov     [rsp+1A0h+HandleInformation], rsi; HANDLE
0x140031562  mov     [rsp+1A0h+Object], r12; PCUNICODE_STRING
0x140031567  call    SrpDisplayAccessReason
0x14003156c  test    r14, r14
0x14003156f  jz      short loc_140031577
0x140031571  mov     eax, [rbp+0A0h+var_AC]
0x140031574  mov     [r14], eax
0x140031577  mov     eax, ebx
0x140031579  mov     rcx, [rbp+0A0h+var_40]
0x14003157d  xor     rcx, rsp; StackCookie
0x140031580  call    __security_check_cookie
0x140031585  mov     rbx, [rsp+1A0h+arg_18]
0x14003158d  add     rsp, 170h
0x140031594  pop     r15
0x140031596  pop     r14
0x140031598  pop     r13
0x14003159a  pop     r12
0x14003159c  pop     rdi
0x14003159d  pop     rsi
0x14003159e  pop     rbp
0x14003159f  retn
```
