# SmartlockerManagedInstallerCheck

- ea: `0x1400315b0`
- end: `0x140031881`
- name: `SmartlockerManagedInstallerCheck`
- size: `721`
- prototype: `__int64 __fastcall(HANDLE, void *, __int64, const UNICODE_STRING *, char, unsigned int *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14002f560`

## callees

- `0x140006a20`
- `0x140006f40`
- `0x140022f7c`
- `0x140023110`
- `0x1400315b0`
- `0x140031890`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140031672`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140031672`
- `ntoskrnl!ObfDereferenceObject` at `0x140031780`
- `ntoskrnl!ObfDereferenceObject` at `0x140031780`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003183e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003183e`
- `ntoskrnl!SeSrpAccessCheck` at `0x14003174a`
- `ntoskrnl!SeSrpAccessCheck` at `0x14003174a`

## pseudocode

```c
__int64 __fastcall SmartlockerManagedInstallerCheck(
        HANDLE a1,
        void *a2,
        __int64 a3,
        const UNICODE_STRING *a4,
        char a5,
        unsigned int *a6,
        _QWORD *a7)
{
  __int64 v7; // rbx
  __int64 v10; // r13
  NTSTATUS v11; // eax
  PVOID v12; // rdi
  int v13; // r8d
  int v14; // eax
  PVOID v15; // rdi
  int v16; // ebx
  unsigned int v17; // esi
  __int64 result; // rax
  int HandleInformation; // [rsp+28h] [rbp-D8h]
  signed int v20; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v21; // [rsp+44h] [rbp-BCh] BYREF
  int v22; // [rsp+48h] [rbp-B8h] BYREF
  PVOID Object; // [rsp+50h] [rbp-B0h] BYREF
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v25; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE v26; // [rsp+70h] [rbp-90h]
  __int128 v27; // [rsp+78h] [rbp-88h] BYREF
  __int128 v28; // [rsp+88h] [rbp-78h]
  __int64 v29; // [rsp+98h] [rbp-68h]
  __int128 v30; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v31; // [rsp+B0h] [rbp-50h]
  _BYTE v32[24]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v33; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v34; // [rsp+E8h] [rbp-18h]
  _DWORD v35[32]; // [rsp+100h] [rbp+0h] BYREF

  v7 = a3 + 144;
  v26 = a2;
  P = 0;
  v21 = 0;
  memset(v35, 0, sizeof(v35));
  v10 = *(_QWORD *)(v7 + 40);
  v29 = 0;
  v22 = 0;
  v33 = 0;
  Object = 0;
  v34 = 0;
  v25 = 0;
  v30 = 0;
  v31 = 0;
  memset(v32, 0, 20);
  v27 = 0;
  v28 = 0;
  v11 = ObReferenceObjectByHandle(a1, 0, 0, 0, &Object, 0);
  v12 = Object;
  v20 = v11;
  if ( v11 >= 0 )
  {
    LOBYTE(HandleInformation) = 1;
    *((_QWORD *)&v25 + 1) = v10 + *(unsigned int *)(v10 + 16);
    v33 = 0u;
    *(_QWORD *)v32 = qword_14000C000;
    *((_QWORD *)&v30 + 1) = &v25;
    *((_QWORD *)&v27 + 1) = &v22;
    v34 = (unsigned __int64)Object;
    *(_QWORD *)&v28 = &v20;
    *((_QWORD *)&v28 + 1) = v35;
    *(_QWORD *)&v25 = 0x300000010LL;
    *(_QWORD *)&v30 = 56;
    *(_OWORD *)&v32[8] = 0;
    v31 = 0x20u;
    *(_QWORD *)&v27 = 0x100000028LL;
    v29 = 0;
    if ( !(unsigned __int8)SeSrpAccessCheck(&v33, 0, &v30, &v27, 0, HandleInformation) && v20 == -1073741790 )
      v20 = (*(_BYTE *)(v10 + 24) & 1) != 0 ? 0xC0000364 : 0;
  }
  if ( v12 )
    ObfDereferenceObject(v12);
  SrpDisplayAccessReason(qword_1400196F8, a4, a1, a5, 0);
  if ( v20 < 0 || (v35[5] & 0x10000) == 0 )
  {
    v16 = -1073741823;
LABEL_16:
    v15 = 0;
    v17 = 0;
    goto LABEL_17;
  }
  v14 = SmartlockerConstructOriginClaim(0, 0, v13, 0, (__int64)a4, (__int64)&v21, (__int64)&P);
  v15 = P;
  v16 = v14;
  if ( v14 < 0
    || (v17 = v21, v16 = SmartlockerTagProcessToken(a1, v21, P), v16 < 0)
    || v26 != a1 && (v16 = SmartlockerTagProcessToken(v26, v17, v15), v16 < 0) )
  {
    if ( v15 )
      ExFreePoolWithTag(v15, 0x41746D73u);
    goto LABEL_16;
  }
LABEL_17:
  *a6 = v17;
  result = (unsigned int)v16;
  *a7 = v15;
  return result;
}

```

## disassembly

```asm
0x1400315b0  push    rbp
0x1400315b2  push    rbx
0x1400315b3  push    rsi
0x1400315b4  push    rdi
0x1400315b5  push    r12
0x1400315b7  push    r13
0x1400315b9  push    r14
0x1400315bb  push    r15
0x1400315bd  lea     rbp, [rsp-98h]
0x1400315c5  sub     rsp, 198h
0x1400315cc  mov     rax, cs:__security_cookie
0x1400315d3  xor     rax, rsp
0x1400315d6  mov     [rbp+0D0h+var_50], rax
0x1400315dd  mov     r14, [rbp+0D0h+arg_28]
0x1400315e4  lea     rbx, [r8+90h]
0x1400315eb  mov     r15, [rbp+0D0h+arg_30]
0x1400315f2  mov     r12, rcx
0x1400315f5  mov     [rsp+1D0h+var_160], rdx
0x1400315fa  lea     rcx, [rbp+0D0h+var_D0]; void *
0x1400315fe  xor     edi, edi
0x140031600  xor     edx, edx; Val
0x140031602  mov     r8d, 80h; Size
0x140031608  mov     [rsp+1D0h+P], rdi
0x14003160d  mov     [rsp+1D0h+var_18C], edi
0x140031611  mov     rsi, r9
0x140031614  call    memset
0x140031619  mov     r13, [rbx+28h]
0x14003161d  xorps   xmm0, xmm0
0x140031620  xor     eax, eax
0x140031622  mov     [rsp+1D0h+HandleInformation], rdi; HandleInformation
0x140031627  mov     [rbp+0D0h+var_100], eax
0x14003162a  xor     r9d, r9d; AccessMode
0x14003162d  mov     [rbp+0D0h+var_138], rax
0x140031631  xor     r8d, r8d; ObjectType
0x140031634  lea     rax, [rsp+1D0h+var_180]
0x140031639  mov     [rsp+1D0h+var_190], edi
0x14003163d  xor     edx, edx; DesiredAccess
0x14003163f  mov     [rsp+1D0h+Object], rax; Object
0x140031644  mov     rcx, r12; Handle
0x140031647  mov     [rsp+1D0h+var_188], edi
0x14003164b  movups  [rbp+0D0h+var_F8], xmm0
0x14003164f  mov     [rsp+1D0h+var_180], rdi
0x140031654  movups  [rbp+0D0h+var_E8], xmm0
0x140031658  movups  [rsp+1D0h+var_170], xmm0
0x14003165d  movups  [rbp+0D0h+var_130], xmm0
0x140031661  movups  [rbp+0D0h+var_120], xmm0
0x140031665  movups  [rbp+0D0h+var_110], xmm0
0x140031669  movups  [rsp+1D0h+var_158], xmm0
0x14003166e  movups  [rbp+0D0h+var_148], xmm0
0x140031672  call    cs:__imp_ObReferenceObjectByHandle
0x140031679  nop     dword ptr [rax+rax+00h]
0x14003167e  mov     rdi, [rsp+1D0h+var_180]
0x140031683  mov     [rsp+1D0h+var_190], eax
0x140031687  test    eax, eax
0x140031689  js      loc_140031778
0x14003168f  mov     eax, [r13+10h]
0x140031693  lea     r9, [rsp+1D0h+var_158]
0x140031698  add     rax, r13
0x14003169b  mov     byte ptr [rsp+1D0h+HandleInformation], 1
0x1400316a0  mov     qword ptr [rsp+1D0h+var_170+8], rax
0x1400316a5  lea     r8, [rbp+0D0h+var_130]
0x1400316a9  lea     rax, qword_14000C000
0x1400316b0  mov     qword ptr [rbp+0D0h+var_F8], 0
0x1400316b8  mov     qword ptr [rbp+0D0h+var_110], rax
0x1400316bc  lea     rcx, [rbp+0D0h+var_F8]
0x1400316c0  lea     rax, [rsp+1D0h+var_170]
0x1400316c5  mov     qword ptr [rbp+0D0h+var_F8+8], 0
0x1400316cd  mov     qword ptr [rbp+0D0h+var_130+8], rax
0x1400316d1  xorps   xmm0, xmm0
0x1400316d4  lea     rax, [rsp+1D0h+var_188]
0x1400316d9  mov     qword ptr [rbp+0D0h+var_E8+8], 0
0x1400316e1  mov     qword ptr [rbp+0D0h+var_158+8], rax
0x1400316e5  xor     edx, edx
0x1400316e7  lea     rax, [rsp+1D0h+var_190]
0x1400316ec  mov     qword ptr [rbp+0D0h+var_E8], rdi
0x1400316f0  mov     qword ptr [rbp+0D0h+var_148], rax
0x1400316f4  lea     rax, [rbp+0D0h+var_D0]
0x1400316f8  mov     qword ptr [rbp+0D0h+var_148+8], rax
0x1400316fc  mov     dword ptr [rsp+1D0h+var_170], 10h
0x140031704  mov     dword ptr [rsp+1D0h+var_170+4], 3
0x14003170c  mov     qword ptr [rbp+0D0h+var_130], 38h ; '8'
0x140031714  mov     qword ptr [rbp+0D0h+var_120+8], 0
0x14003171c  movdqu  [rbp+0D0h+var_110+8], xmm0
0x140031721  mov     qword ptr [rbp+0D0h+var_120], 20h ; ' '
0x140031729  mov     dword ptr [rsp+1D0h+var_158], 28h ; '('
0x140031731  mov     dword ptr [rsp+1D0h+var_158+4], 1
0x140031739  mov     [rbp+0D0h+var_138], 0
0x140031741  mov     [rsp+1D0h+Object], 0
0x14003174a  call    cs:__imp_SeSrpAccessCheck
0x140031751  nop     dword ptr [rax+rax+00h]
0x140031756  test    al, al
0x140031758  jnz     short loc_140031778
0x14003175a  cmp     [rsp+1D0h+var_190], 0C0000022h
0x140031762  jnz     short loc_140031778
0x140031764  movzx   eax, byte ptr [r13+18h]
0x140031769  and     al, 1
0x14003176b  neg     al
0x14003176d  sbb     eax, eax
0x14003176f  and     eax, 0C0000364h
0x140031774  mov     [rsp+1D0h+var_190], eax
0x140031778  test    rdi, rdi
0x14003177b  jz      short loc_14003178C
0x14003177d  mov     rcx, rdi; Object
0x140031780  call    cs:__imp_ObfDereferenceObject
0x140031787  nop     dword ptr [rax+rax+00h]
0x14003178c  mov     eax, dword ptr [rbp+0D0h+arg_20]
0x140031792  mov     r8, rbx
0x140031795  mov     r9d, [rbp+0D0h+var_BC]
0x140031799  mov     rdx, [rbx+28h]
0x14003179d  mov     rcx, cs:qword_1400196F8; RegHandle
0x1400317a4  mov     [rsp+1D0h+var_198], 0; char
0x1400317a9  mov     dword ptr [rsp+1D0h+var_1A0], eax; char
0x1400317ad  mov     [rsp+1D0h+HandleInformation], r12; HANDLE
0x1400317b2  mov     [rsp+1D0h+Object], rsi; PCUNICODE_STRING
0x1400317b7  call    SrpDisplayAccessReason
0x1400317bc  cmp     [rsp+1D0h+var_190], 0
0x1400317c1  jl      loc_14003184C
0x1400317c7  test    [rbp+0D0h+var_BC], 10000h
0x1400317ce  jz      short loc_14003184C
0x1400317d0  lea     rax, [rsp+1D0h+P]
0x1400317d5  xor     r9d, r9d
0x1400317d8  mov     qword ptr [rsp+1D0h+var_1A0], rax
0x1400317dd  xor     edx, edx
0x1400317df  lea     rax, [rsp+1D0h+var_18C]
0x1400317e4  xor     ecx, ecx
0x1400317e6  mov     [rsp+1D0h+HandleInformation], rax
0x1400317eb  mov     [rsp+1D0h+Object], rsi
0x1400317f0  call    SmartlockerConstructOriginClaim
0x1400317f5  mov     rdi, [rsp+1D0h+P]
0x1400317fa  mov     ebx, eax
0x1400317fc  test    eax, eax
0x1400317fe  js      short loc_140031831
0x140031800  mov     esi, [rsp+1D0h+var_18C]
0x140031804  mov     r8, rdi
0x140031807  mov     edx, esi
0x140031809  mov     rcx, r12
0x14003180c  call    SmartlockerTagProcessToken
0x140031811  mov     ebx, eax
0x140031813  test    eax, eax
0x140031815  js      short loc_140031831
0x140031817  mov     rcx, [rsp+1D0h+var_160]
0x14003181c  cmp     rcx, r12
0x14003181f  jz      short loc_140031855
0x140031821  mov     r8, rdi
0x140031824  mov     edx, esi
0x140031826  call    SmartlockerTagProcessToken
0x14003182b  mov     ebx, eax
0x14003182d  test    eax, eax
0x14003182f  jns     short loc_140031855
0x140031831  test    rdi, rdi
0x140031834  jz      short loc_140031851
0x140031836  mov     edx, 41746D73h; Tag
0x14003183b  mov     rcx, rdi; P
0x14003183e  call    cs:__imp_ExFreePoolWithTag
0x140031845  nop     dword ptr [rax+rax+00h]
0x14003184a  jmp     short loc_140031851
0x14003184c  mov     ebx, 0C0000001h
0x140031851  xor     edi, edi
0x140031853  xor     esi, esi
0x140031855  mov     [r14], esi
0x140031858  mov     eax, ebx
0x14003185a  mov     [r15], rdi
0x14003185d  mov     rcx, [rbp+0D0h+var_50]
0x140031864  xor     rcx, rsp; StackCookie
0x140031867  call    __security_check_cookie
0x14003186c  add     rsp, 198h
0x140031873  pop     r15
0x140031875  pop     r14
0x140031877  pop     r13
0x140031879  pop     r12
0x14003187b  pop     rdi
0x14003187c  pop     rsi
0x14003187d  pop     rbx
0x14003187e  pop     rbp
0x14003187f  retn
```
