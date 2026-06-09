# CProviderRegistrationCache::CallLsarLookupSids(void *,ushort * *,ushort * *)

- ea: `0x180014088`
- end: `0x180014261`
- name: `?CallLsarLookupSids@CProviderRegistrationCache@@AEAAKPEAXPEAPEAG1@Z`
- size: `473`
- prototype: `__int64 __fastcall(__int64 (__fastcall **this)(__int64 *), void *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800157d4`

## callees

- `0x180003dc0`
- `0x180007ea0`
- `0x18000c344`
- `0x18000e8d6`
- `0x180014088`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800141c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800141c5`

## string_xrefs

- `0x18001413d`: `LsaIOpenPolicyTrusted`
- `0x1800140f1`: `CProviderRegistrationCache::CallLsarLookupSids`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::CallLsarLookupSids(
        __int64 (__fastcall **this)(__int64 *),
        void *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  _DWORD *v10; // rcx
  int v11; // eax
  unsigned int v12; // ebx
  const void *v13; // r14
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rsi
  unsigned int v16; // ebx
  void *v18; // [rsp+40h] [rbp-29h] BYREF
  __int128 v19; // [rsp+48h] [rbp-21h] BYREF
  _DWORD v20[2]; // [rsp+58h] [rbp-11h] BYREF
  void **v21; // [rsp+60h] [rbp-9h]
  _BYTE v22[88]; // [rsp+68h] [rbp-1h] BYREF
  int v23; // [rsp+D0h] [rbp+67h] BYREF
  _DWORD *v24; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v25; // [rsp+E0h] [rbp+77h] BYREF
  unsigned int v26; // [rsp+E8h] [rbp+7Fh] BYREF
  int v27; // [rsp+ECh] [rbp+83h]

  v27 = HIDWORD(a4);
  v26 = 0;
  v24 = 0;
  v20[1] = 0;
  v23 = 0;
  v25 = 0;
  *a3 = 0;
  CLogETWBlock::CLogETWBlock((CLogETWBlock *)v22, "CProviderRegistrationCache::CallLsarLookupSids", (int *)a3, 0, &v26);
  v20[0] = 1;
  v21 = &v18;
  v18 = a2;
  v19 = 0;
  v7 = this[27](&v25);
  if ( v7 < 0 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v9, v8, "LsaIOpenPolicyTrusted", (unsigned int)v7);
    v26 = 50;
LABEL_5:
    v10 = v24;
    goto LABEL_19;
  }
  v11 = ((__int64 (__fastcall *)(__int64, _DWORD *, _DWORD **, __int128 *, int, int *))this[26])(
          v25,
          v20,
          &v24,
          &v19,
          1,
          &v23);
  v10 = v24;
  if ( v11 >= 0 && v23 && (_DWORD)v19 && v24 && *v24 )
  {
    v12 = *(unsigned __int16 *)(*((_QWORD *)&v19 + 1) + 8LL) >> 1;
    if ( v12 + 1 >= v12 )
    {
      v13 = *(const void **)(*((_QWORD *)&v19 + 1) + 16LL);
      v14 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v12 + 1));
      v15 = v14;
      if ( v14 )
      {
        if ( v13 )
          memcpy_0(v14, v13, 2LL * v12);
        v26 = 0;
        *a3 = v15;
      }
      else
      {
        v26 = 14;
      }
      goto LABEL_5;
    }
    v26 = 534;
  }
  else
  {
    v26 = 1168;
  }
LABEL_19:
  if ( v10 )
    ((void (*)(void))this[29])();
  this[30]((__int64 *)&v19);
  if ( v25 )
    this[28](&v25);
  v16 = v26;
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)v22);
  return v16;
}

```

## disassembly

```asm
0x180014088  mov     qword ptr [rsp-8+arg_18], r9
0x18001408d  push    rbp
0x18001408e  push    rbx
0x18001408f  push    rsi
0x180014090  push    rdi
0x180014091  push    r14
0x180014093  push    r15
0x180014095  lea     rbp, [rsp-2Fh]
0x18001409a  sub     rsp, 98h
0x1800140a1  mov     r15, r8
0x1800140a4  mov     rbx, rdx
0x1800140a7  mov     rdi, rcx
0x1800140aa  mov     [rbp+57h+arg_18], 0
0x1800140b1  mov     [rbp+57h+arg_8], 0
0x1800140b9  xorps   xmm0, xmm0
0x1800140bc  movups  [rbp+57h+var_78], xmm0
0x1800140c0  xorps   xmm1, xmm1
0x1800140c3  movups  [rbp+57h+var_68], xmm1
0x1800140c7  mov     [rbp+57h+var_80], 0
0x1800140cf  mov     [rbp+57h+arg_0], 0
0x1800140d6  mov     [rbp+57h+arg_10], 0
0x1800140de  mov     qword ptr [r8], 0
0x1800140e5  lea     rax, [rbp+57h+arg_18]
0x1800140e9  mov     [rsp+0C0h+var_A0], rax; unsigned int *
0x1800140ee  xor     r9d, r9d; int *
0x1800140f1  lea     rdx, aCproviderregis_10; "CProviderRegistrationCache::CallLsarLoo"...
0x1800140f8  lea     rcx, [rbp+57h+var_58]; this
0x1800140fc  call    ??0CLogETWBlock@@QEAA@PEBDPEAJ1PEAK@Z; CLogETWBlock::CLogETWBlock(char const *,long *,long *,ulong *)
0x180014101  nop
0x180014102  mov     esi, 1
0x180014107  mov     dword ptr [rbp+57h+var_68], esi
0x18001410a  lea     rax, [rbp+57h+var_80]
0x18001410e  mov     qword ptr [rbp+57h+var_68+8], rax
0x180014112  mov     [rbp+57h+var_80], rbx
0x180014116  xorps   xmm0, xmm0
0x180014119  movups  [rbp+57h+var_78], xmm0
0x18001411d  lea     rcx, [rbp+57h+arg_10]
0x180014121  mov     rax, [rdi+0D8h]
0x180014128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001412d  test    eax, eax
0x18001412f  jns     short loc_180014159
0x180014131  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180014138  jz      short loc_180014149
0x18001413a  mov     r9d, eax
0x18001413d  lea     r8, aLsaiopenpolicy; "LsaIOpenPolicyTrusted"
0x180014144  call    McTemplateU0sq_EtwEventWriteTransfer
0x180014149  mov     [rbp+57h+arg_18], 32h ; '2'
0x180014150  mov     rcx, [rbp+57h+arg_8]
0x180014154  jmp     loc_18001420B
0x180014159  lea     rax, [rbp+57h+arg_0]
0x18001415d  mov     [rsp+0C0h+var_98], rax
0x180014162  mov     dword ptr [rsp+0C0h+var_A0], esi
0x180014166  lea     r9, [rbp+57h+var_78]
0x18001416a  lea     r8, [rbp+57h+arg_8]
0x18001416e  lea     rdx, [rbp+57h+var_68]
0x180014172  mov     rcx, [rbp+57h+arg_10]
0x180014176  mov     rax, [rdi+0D0h]
0x18001417d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014182  mov     rcx, [rbp+57h+arg_8]
0x180014186  test    eax, eax
0x180014188  js      short loc_180014204
0x18001418a  cmp     [rbp+57h+arg_0], 0
0x18001418e  jz      short loc_180014204
0x180014190  cmp     dword ptr [rbp+57h+var_78], 0
0x180014194  jz      short loc_180014204
0x180014196  test    rcx, rcx
0x180014199  jz      short loc_180014204
0x18001419b  cmp     dword ptr [rcx], 0
0x18001419e  jz      short loc_180014204
0x1800141a0  mov     rax, qword ptr [rbp+57h+var_78+8]
0x1800141a4  movzx   ebx, word ptr [rax+8]
0x1800141a8  shr     ebx, 1
0x1800141aa  lea     edx, [rbx+1]
0x1800141ad  cmp     edx, ebx
0x1800141af  jnb     short loc_1800141BA
0x1800141b1  mov     [rbp+57h+arg_18], 216h
0x1800141b8  jmp     short loc_18001420B
0x1800141ba  mov     r14, [rax+10h]
0x1800141be  add     edx, edx; uBytes
0x1800141c0  mov     ecx, 40h ; '@'; uFlags
0x1800141c5  call    cs:__imp_LocalAlloc
0x1800141cb  mov     rsi, rax
0x1800141ce  test    rax, rax
0x1800141d1  jnz     short loc_1800141DF
0x1800141d3  mov     [rbp+57h+arg_18], 0Eh
0x1800141da  jmp     loc_180014150
0x1800141df  test    r14, r14
0x1800141e2  jz      short loc_1800141F5
0x1800141e4  mov     r8d, ebx
0x1800141e7  add     r8, r8; Size
0x1800141ea  mov     rdx, r14; Src
0x1800141ed  mov     rcx, rsi; void *
0x1800141f0  call    memcpy_0
0x1800141f5  mov     [rbp+57h+arg_18], 0
0x1800141fc  mov     [r15], rsi
0x1800141ff  jmp     loc_180014150
0x180014204  mov     [rbp+57h+arg_18], 490h
0x18001420b  test    rcx, rcx
0x18001420e  jz      short loc_18001421C
0x180014210  mov     rax, [rdi+0E8h]
0x180014217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001421c  lea     rcx, [rbp+57h+var_78]
0x180014220  mov     rax, [rdi+0F0h]
0x180014227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001422c  cmp     [rbp+57h+arg_10], 0
0x180014231  jz      short loc_180014243
0x180014233  lea     rcx, [rbp+57h+arg_10]
0x180014237  mov     rax, [rdi+0E0h]
0x18001423e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014243  mov     ebx, [rbp+57h+arg_18]
0x180014246  lea     rcx, [rbp+57h+var_58]; this
0x18001424a  call    ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
0x18001424f  mov     eax, ebx
0x180014251  add     rsp, 98h
0x180014258  pop     r15
0x18001425a  pop     r14
0x18001425c  pop     rdi
0x18001425d  pop     rsi
0x18001425e  pop     rbx
0x18001425f  pop     rbp
0x180014260  retn
```
