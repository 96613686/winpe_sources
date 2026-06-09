# CManagedAppProcessor::GetRemovedApps(void)

- ea: `0x180010f60`
- end: `0x180011261`
- name: `?GetRemovedApps@CManagedAppProcessor@@AEAAKXZ`
- size: `769`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b7e8`

## callees

- `0x1800016d0`
- `0x180002024`
- `0x180002b14`
- `0x180007de4`
- `0x18000a2cc`
- `0x18000fe58`
- `0x180010ae8`
- `0x180010f60`
- `0x18001b1a0`
- `0x18001c0e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011038`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800111f2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011219`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800111f2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011219`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180011010`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180011010`
- `KERNEL32!lstrcmpiW` at `0x1800110c7`
- `KERNEL32!lstrcmpiW` at `0x1800110c7`

## pseudocode

```c
__int64 __fastcall CManagedAppProcessor::GetRemovedApps(HANDLE *this)
{
  DWORD OrderedLocalAppList; // edi
  _DWORD *v3; // r14
  DWORD LastError; // eax
  LPCWSTR *i; // rsi
  __int64 v6; // rdx
  __int64 *v7; // rcx
  __int64 *v8; // rdi
  int v9; // eax
  _QWORD v11[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v12; // [rsp+30h] [rbp-D0h]
  __int128 v13; // [rsp+40h] [rbp-C0h]
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v15; // [rsp+58h] [rbp-A8h]
  unsigned __int128 v16; // [rsp+60h] [rbp-A0h]
  __int128 v17; // [rsp+70h] [rbp-90h]
  int v18; // [rsp+80h] [rbp-80h]
  int v19; // [rsp+84h] [rbp-7Ch]
  _BYTE v20[16]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v21; // [rsp+A0h] [rbp-60h]

  v16 = 0;
  v15 = &v14;
  v14 = (__int64)&v14;
  v11[1] = 0;
  v12 = 0;
  v13 = 0;
  v11[0] = &CAppList::`vftable';
  v17 = 0;
  v18 = -2147467259;
  v19 = 0;
  OrderedLocalAppList = CManagedAppProcessor::GetOrderedLocalAppList(
                          (CManagedAppProcessor *)this,
                          (struct CAppList *)v11);
  if ( OrderedLocalAppList )
    goto LABEL_39;
  v3 = this + 37;
  if ( *((_DWORD *)this + 99) != 1 && *v3 && !ImpersonateLoggedOnUser(this[33]) )
  {
    if ( *(_DWORD *)&gDebugLevel )
    {
      LastError = GetLastError();
      _DebugMsg(OrderedLocalAppList + 2, 0xBC4u, LastError);
    }
    OrderedLocalAppList = GetLastError();
    if ( OrderedLocalAppList )
    {
LABEL_39:
      CAppList::~CAppList((CAppList *)v11);
      return OrderedLocalAppList;
    }
  }
  this[3] = this[2];
  for ( i = (LPCWSTR *)this[1]; ; i = (LPCWSTR *)*((_QWORD *)this[2] + 1) )
  {
    this[2] = i;
    if ( i == (LPCWSTR *)this )
      i = 0;
    if ( !i )
    {
      this[2] = this[3];
      if ( *((_DWORD *)this + 99) != 1 )
      {
        if ( *v3 )
          RevertToSelf();
      }
      CAppList::~CAppList((CAppList *)v11);
      return 0;
    }
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xBC2u, i[3]);
    v6 = v16;
    v7 = v15;
    v16 = __PAIR128__(v16, (unsigned __int64)v15);
    v8 = v15;
    if ( v15 == &v14 )
      v8 = 0;
    if ( v8 )
      break;
LABEL_27:
    *(_QWORD *)&v16 = v6;
  }
  while ( 1 )
  {
    if ( (v8[28] & 0x43) == 0 || (v8[28] & 0x440) == 0x40 )
      goto LABEL_23;
    if ( !lstrcmpiW((LPCWSTR)v8[6], i[2]) )
      break;
    v7 = (__int64 *)v16;
LABEL_23:
    v7 = (__int64 *)v7[1];
    *(_QWORD *)&v16 = v7;
LABEL_24:
    v8 = v7;
    if ( v7 == &v14 || !v7 )
    {
      v6 = *((_QWORD *)&v16 + 1);
      goto LABEL_27;
    }
  }
  v9 = *((_DWORD *)v8 + 56);
  if ( (v9 & 0x10) == 0
    || (v9 & 0x400) != 0
    || (memset_0(v20, 0, 0xD0u),
        (unsigned int)CManagedAppProcessor::GetDsPackageFromGPO(
                        (CManagedAppProcessor *)this,
                        (struct CGPOInfo *)i,
                        (struct _GUID *)(v8 + 3),
                        (struct tagPACKAGEDISPINFO *)v20))
    || (v8[12] = (__int64)StringDuplicate(v21), ReleasePackageInfo(v20), v8[12]) )
  {
    CAppInfo::SetAction(v8, ((v8[28] & 0x10) == 0) | 4u, 5);
    *(_QWORD *)&v16 = *(_QWORD *)(v16 + 8);
    *(_QWORD *)(*v8 + 8) = v8[1];
    *(_QWORD *)v8[1] = *v8;
    v8[1] = (__int64)(this + 10);
    *v8 = (__int64)this[10];
    *((_QWORD *)this[10] + 1) = v8;
    this[10] = v8;
    v7 = (__int64 *)v16;
    goto LABEL_24;
  }
  if ( *((_DWORD *)this + 99) != 1 && *((_DWORD *)this + 74) )
    RevertToSelf();
  CAppList::~CAppList((CAppList *)v11);
  return 14;
}

```

## disassembly

```asm
0x180010f60  mov     [rsp-8+arg_8], rbx
0x180010f65  mov     [rsp-8+arg_10], rsi
0x180010f6a  push    rbp
0x180010f6b  push    rdi
0x180010f6c  push    r14
0x180010f6e  lea     rbp, [rsp-70h]
0x180010f73  sub     rsp, 170h
0x180010f7a  mov     rax, cs:__security_cookie
0x180010f81  xor     rax, rsp
0x180010f84  mov     [rbp+80h+var_20], rax
0x180010f88  mov     rbx, rcx
0x180010f8b  xorps   xmm0, xmm0
0x180010f8e  movdqa  [rsp+180h+var_120], xmm0
0x180010f94  lea     rax, [rsp+180h+var_130]
0x180010f99  mov     [rsp+180h+var_128], rax
0x180010f9e  lea     rax, [rsp+180h+var_130]
0x180010fa3  mov     [rsp+180h+var_130], rax
0x180010fa8  mov     [rsp+180h+var_158], 0
0x180010fb1  movdqa  [rsp+180h+var_150], xmm0
0x180010fb7  xorps   xmm1, xmm1
0x180010fba  movdqa  [rsp+180h+var_140], xmm1
0x180010fc0  lea     rax, ??_7CAppList@@6B@; const CAppList::`vftable'
0x180010fc7  mov     [rsp+180h+var_160], rax
0x180010fcc  movdqa  [rsp+180h+var_110], xmm0
0x180010fd2  mov     [rbp+80h+var_100], 80004005h
0x180010fd9  mov     [rbp+80h+var_FC], 0
0x180010fe0  lea     rdx, [rsp+180h+var_160]; struct CAppList *
0x180010fe5  call    ?GetOrderedLocalAppList@CManagedAppProcessor@@QEAAKAEAVCAppList@@@Z; CManagedAppProcessor::GetOrderedLocalAppList(CAppList &)
0x180010fea  mov     edi, eax
0x180010fec  test    eax, eax
0x180010fee  jnz     loc_180011231
0x180010ff4  lea     r14, [rbx+128h]
0x180010ffb  cmp     dword ptr [rbx+18Ch], 1
0x180011002  jz      short loc_180011048
0x180011004  cmp     [r14], eax
0x180011007  jz      short loc_180011048
0x180011009  mov     rcx, [rbx+108h]; hToken
0x180011010  call    cs:__imp_ImpersonateLoggedOnUser
0x180011016  test    eax, eax
0x180011018  jnz     short loc_180011048
0x18001101a  cmp     cs:?gDebugLevel@@3KA, eax; ulong gDebugLevel
0x180011020  jz      short loc_180011038
0x180011022  call    cs:__imp_GetLastError
0x180011028  mov     r8d, eax
0x18001102b  mov     edx, 0BC4h; unsigned int
0x180011030  lea     ecx, [rdi+2]; unsigned int
0x180011033  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180011038  call    cs:__imp_GetLastError
0x18001103e  mov     edi, eax
0x180011040  test    eax, eax
0x180011042  jnz     loc_180011231
0x180011048  mov     rax, [rbx+10h]
0x18001104c  mov     [rbx+18h], rax
0x180011050  mov     rsi, [rbx+8]
0x180011054  jmp     loc_1800111C6
0x180011059  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x180011060  jz      short loc_180011075
0x180011062  mov     r8, [rsi+18h]
0x180011066  mov     edx, 0BC2h; unsigned int
0x18001106b  mov     ecx, 4; unsigned int
0x180011070  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180011075  mov     rdx, qword ptr [rsp+180h+var_120]
0x18001107a  mov     qword ptr [rsp+180h+var_120+8], rdx
0x18001107f  mov     rcx, [rsp+180h+var_128]
0x180011084  mov     qword ptr [rsp+180h+var_120], rcx
0x180011089  mov     rdi, rcx
0x18001108c  xor     eax, eax
0x18001108e  lea     r8, [rsp+180h+var_130]
0x180011093  cmp     rcx, r8
0x180011096  cmovz   rdi, rax
0x18001109a  test    rdi, rdi
0x18001109d  jz      loc_1800111B9
0x1800110a3  mov     eax, [rdi+0E0h]
0x1800110a9  test    al, 43h
0x1800110ab  jz      loc_180011195
0x1800110b1  and     eax, 440h
0x1800110b6  cmp     eax, 40h ; '@'
0x1800110b9  jz      loc_180011195
0x1800110bf  mov     rdx, [rsi+10h]; lpString2
0x1800110c3  mov     rcx, [rdi+30h]; lpString1
0x1800110c7  call    cs:__imp_lstrcmpiW
0x1800110cd  test    eax, eax
0x1800110cf  jnz     loc_180011190
0x1800110d5  mov     eax, [rdi+0E0h]
0x1800110db  test    al, 10h
0x1800110dd  jz      short loc_18001112E
0x1800110df  bt      eax, 0Ah
0x1800110e3  jb      short loc_18001112E
0x1800110e5  xor     edx, edx; Val
0x1800110e7  mov     r8d, 0D0h; Size
0x1800110ed  lea     rcx, [rbp+80h+var_F0]; void *
0x1800110f1  call    memset_0
0x1800110f6  lea     r8, [rdi+18h]; struct _GUID *
0x1800110fa  lea     r9, [rbp+80h+var_F0]; struct tagPACKAGEDISPINFO *
0x1800110fe  mov     rdx, rsi; struct CGPOInfo *
0x180011101  mov     rcx, rbx; this
0x180011104  call    ?GetDsPackageFromGPO@CManagedAppProcessor@@AEAAJPEAVCGPOInfo@@PEAU_GUID@@PEAUtagPACKAGEDISPINFO@@@Z; CManagedAppProcessor::GetDsPackageFromGPO(CGPOInfo *,_GUID *,tagPACKAGEDISPINFO *)
0x180011109  test    eax, eax
0x18001110b  jnz     short loc_18001112E
0x18001110d  mov     rcx, [rbp+80h+var_E0]; unsigned __int16 *
0x180011111  call    ?StringDuplicate@@YAPEAGPEBG@Z; StringDuplicate(ushort const *)
0x180011116  mov     [rdi+60h], rax
0x18001111a  lea     rcx, [rbp+80h+var_F0]; void *
0x18001111e  call    ReleasePackageInfo
0x180011123  cmp     qword ptr [rdi+60h], 0
0x180011128  jz      loc_180011207
0x18001112e  mov     edx, [rdi+0E0h]
0x180011134  shr     edx, 4
0x180011137  not     edx
0x180011139  and     edx, 1
0x18001113c  or      edx, 4
0x18001113f  xor     r9d, r9d
0x180011142  lea     r8d, [r9+5]
0x180011146  mov     rcx, rdi
0x180011149  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x18001114e  mov     rax, qword ptr [rsp+180h+var_120]
0x180011153  mov     rcx, [rax+8]
0x180011157  mov     qword ptr [rsp+180h+var_120], rcx
0x18001115c  mov     rcx, [rdi]
0x18001115f  mov     rax, [rdi+8]
0x180011163  mov     [rcx+8], rax
0x180011167  mov     rcx, [rdi+8]
0x18001116b  mov     rax, [rdi]
0x18001116e  mov     [rcx], rax
0x180011171  lea     rcx, [rbx+50h]
0x180011175  mov     [rdi+8], rcx
0x180011179  mov     rax, [rcx]
0x18001117c  mov     [rdi], rax
0x18001117f  mov     rax, [rcx]
0x180011182  mov     [rax+8], rdi
0x180011186  mov     [rcx], rdi
0x180011189  mov     rcx, qword ptr [rsp+180h+var_120]
0x18001118e  jmp     short loc_18001119E
0x180011190  mov     rcx, qword ptr [rsp+180h+var_120]
0x180011195  mov     rcx, [rcx+8]
0x180011199  mov     qword ptr [rsp+180h+var_120], rcx
0x18001119e  mov     rdi, rcx
0x1800111a1  lea     rax, [rsp+180h+var_130]
0x1800111a6  cmp     rcx, rax
0x1800111a9  jz      short loc_1800111B4
0x1800111ab  test    rcx, rcx
0x1800111ae  jnz     loc_1800110A3
0x1800111b4  mov     rdx, qword ptr [rsp+180h+var_120+8]
0x1800111b9  mov     qword ptr [rsp+180h+var_120], rdx
0x1800111be  mov     rax, [rbx+10h]
0x1800111c2  mov     rsi, [rax+8]
0x1800111c6  xor     eax, eax
0x1800111c8  mov     [rbx+10h], rsi
0x1800111cc  cmp     rsi, rbx
0x1800111cf  cmovz   rsi, rax
0x1800111d3  test    rsi, rsi
0x1800111d6  jnz     loc_180011059
0x1800111dc  mov     rax, [rbx+18h]
0x1800111e0  mov     [rbx+10h], rax
0x1800111e4  cmp     dword ptr [rbx+18Ch], 1
0x1800111eb  jz      short loc_1800111F9
0x1800111ed  cmp     [r14], esi
0x1800111f0  jz      short loc_1800111F9
0x1800111f2  call    cs:__imp_RevertToSelf
0x1800111f8  nop
0x1800111f9  lea     rcx, [rsp+180h+var_160]; this
0x1800111fe  call    ??1CAppList@@UEAA@XZ; CAppList::~CAppList(void)
0x180011203  xor     eax, eax
0x180011205  jmp     short loc_18001123D
0x180011207  cmp     dword ptr [rbx+18Ch], 1
0x18001120e  jz      short loc_180011220
0x180011210  cmp     dword ptr [rbx+128h], 0
0x180011217  jz      short loc_180011220
0x180011219  call    cs:__imp_RevertToSelf
0x18001121f  nop
0x180011220  lea     rcx, [rsp+180h+var_160]; this
0x180011225  call    ??1CAppList@@UEAA@XZ; CAppList::~CAppList(void)
0x18001122a  mov     eax, 0Eh
0x18001122f  jmp     short loc_18001123D
0x180011231  lea     rcx, [rsp+180h+var_160]; this
0x180011236  call    ??1CAppList@@UEAA@XZ; CAppList::~CAppList(void)
0x18001123b  mov     eax, edi
0x18001123d  mov     rcx, [rbp+80h+var_20]
0x180011241  xor     rcx, rsp; StackCookie
0x180011244  call    __security_check_cookie
0x180011249  lea     r11, [rsp+180h+var_10]
0x180011251  mov     rbx, [r11+28h]
0x180011255  mov     rsi, [r11+30h]
0x180011259  mov     rsp, r11
0x18001125c  pop     r14
0x18001125e  pop     rdi
0x18001125f  pop     rbp
0x180011260  retn
```
