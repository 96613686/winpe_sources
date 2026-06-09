# Broker::ApplicationStateTable::CreateApplicationState(Broker::ApplicationIdentity const &)

- ea: `0x180007880`
- end: `0x180007c41`
- name: `?CreateApplicationState@ApplicationStateTable@Broker@@QEAA?AV?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@AEBUApplicationIdentity@2@@Z`
- size: `961`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180006e00`

## callees

- `0x180001e40`
- `0x1800076a0`
- `0x180007880`
- `0x18000f370`
- `0x1800133c0`
- `0x18001732c`
- `0x18001a054`
- `0x18001aa38`
- `0x18001cf50`
- `0x18001cf74`
- `0x18001d9ac`
- `0x180022434`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180007953`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180007ae3`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180007953`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180007ae3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Broker::ApplicationStateTable::CreateApplicationState(_QWORD *a1, _QWORD *a2, __int64 a3)
{
  __int64 *v5; // r14
  __int64 *v6; // rsi
  __int64 *v7; // rbx
  bool v8; // zf
  size_t v9; // r8
  const void *v10; // rdx
  int v11; // edi
  const WCHAR *lpString2; // rax
  const WCHAR *v13; // r8
  int v14; // ecx
  int v15; // eax
  std::_Ref_count_base *v16; // rcx
  const void *v17; // rdx
  size_t v18; // rax
  size_t v19; // r8
  int v20; // ebx
  const WCHAR *v21; // rax
  const WCHAR *v22; // r8
  int v23; // ecx
  int v24; // ecx
  __int64 v25; // rax
  __int64 v26; // rcx
  volatile signed __int32 *v27; // rbx
  int v29; // eax
  int v30; // ecx
  _DWORD *v31; // [rsp+58h] [rbp-100h]
  _QWORD *v32[3]; // [rsp+60h] [rbp-F8h] BYREF
  _BYTE pExceptionObject[12]; // [rsp+78h] [rbp-E0h] BYREF
  int v34; // [rsp+84h] [rbp-D4h]
  _BYTE v35[88]; // [rsp+A0h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+F8h] [rbp-60h] BYREF
  std::_Ref_count_base *v37; // [rsp+100h] [rbp-58h]

  v32[0] = a1;
  v32[2] = a2;
  *a2 = 0;
  a2[1] = 0;
  v5 = a1 + 4;
  v6 = (__int64 *)a1[4];
  v7 = (__int64 *)v6[1];
  v34 = 0;
  v8 = *((_BYTE *)v7 + 25) == 0;
  while ( v8 )
  {
    v9 = v7[5] - v7[4];
    v10 = *(const void **)a3;
    if ( v9 >= *(_QWORD *)(a3 + 8) - *(_QWORD *)a3 )
    {
      if ( v9 <= *(_QWORD *)(a3 + 8) - (_QWORD)v10 )
      {
        v15 = memcmp_0((const void *)v7[4], v10, v9);
        if ( v15 < 0 )
          v11 = -1;
        else
          v11 = v15 > 0;
      }
      else
      {
        v11 = 1;
      }
    }
    else
    {
      v11 = -1;
    }
    if ( *(_QWORD *)(a3 + 48) <= 7u )
      lpString2 = (const WCHAR *)(a3 + 24);
    else
      lpString2 = *(const WCHAR **)(a3 + 24);
    v13 = (const WCHAR *)(v7 + 7);
    if ( (unsigned __int64)v7[10] > 7 )
      v13 = *(const WCHAR **)v13;
    v14 = CompareStringEx(&LocaleName, 1u, v13, *((_DWORD *)v7 + 18), lpString2, *(_DWORD *)(a3 + 40), 0, 0, 0);
    if ( v14 == 1 )
    {
LABEL_10:
      v7 = (__int64 *)v7[2];
      v8 = *((_BYTE *)v7 + 25) == 0;
    }
    else
    {
      v30 = v14 - 2;
      if ( v30 )
      {
        if ( v30 != 1 )
        {
          Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
          throw (Broker::Win32Error *)pExceptionObject;
        }
      }
      else if ( v11 == -1 )
      {
        goto LABEL_10;
      }
      v6 = v7;
      v7 = (__int64 *)*v7;
      v8 = *((_BYTE *)v7 + 25) == 0;
    }
  }
  if ( *((_BYTE *)v6 + 25) )
    goto LABEL_17;
  v17 = (const void *)v6[4];
  v18 = v6[5] - (_QWORD)v17;
  v19 = *(_QWORD *)(a3 + 8) - *(_QWORD *)a3;
  if ( v19 >= v18 )
  {
    if ( v19 <= v18 )
    {
      v29 = memcmp_0(*(const void **)a3, v17, v19);
      if ( v29 < 0 )
        v20 = -1;
      else
        v20 = v29 > 0;
    }
    else
    {
      v20 = 1;
    }
  }
  else
  {
    v20 = -1;
  }
  v21 = (const WCHAR *)(v6 + 7);
  if ( (unsigned __int64)v6[10] > 7 )
    v21 = *(const WCHAR **)v21;
  v22 = (const WCHAR *)(a3 + 24);
  if ( *(_QWORD *)(a3 + 48) > 7u )
    v22 = *(const WCHAR **)v22;
  v23 = CompareStringEx(&LocaleName, 1u, v22, *(_DWORD *)(a3 + 40), v21, *((_DWORD *)v6 + 18), 0, 0, 0);
  if ( v23 == 1 )
  {
LABEL_17:
    v31 = operator new(0xA8u);
    *(_OWORD *)v31 = 0;
    v31[2] = 1;
    v31[3] = 1;
    *(_QWORD *)v31 = &std::_Ref_count_obj2<Broker::ApplicationStateTable::State>::`vftable';
    Broker::ApplicationStateTable::State::State(
      (__int64)(v31 + 4),
      (const struct Broker::ApplicationIdentity *)a3,
      v32[0]);
    *a2 = v31 + 4;
    v16 = (std::_Ref_count_base *)a2[1];
    a2[1] = v31;
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    Broker::ApplicationIdentity::ApplicationIdentity(
      (Broker::ApplicationIdentity *)v35,
      (const struct Broker::ApplicationIdentity *)a3);
    std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(&v36, a2);
    std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::_Emplace<std::pair<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>>>(
      v5,
      (__int64)v32,
      (__int64)v35);
    if ( v37 )
      std::_Ref_count_base::_Decref(v37);
    Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v35);
    return a2;
  }
  v24 = v23 - 2;
  if ( !v24 )
  {
    if ( v20 != -1 )
      goto LABEL_35;
    goto LABEL_17;
  }
  if ( v24 != 1 )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
    throw (Broker::Win32Error *)pExceptionObject;
  }
LABEL_35:
  if ( v6 == (__int64 *)*v5 )
    goto LABEL_17;
  v25 = v6[16];
  if ( v25 )
    _InterlockedIncrement((volatile signed __int32 *)(v25 + 8));
  v26 = v6[16];
  *a2 = v6[15];
  v27 = (volatile signed __int32 *)a2[1];
  a2[1] = v26;
  if ( v27 )
  {
    if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
      if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180007880  mov     [rsp+arg_18], rbx
0x180007885  push    rbp
0x180007886  push    rsi
0x180007887  push    rdi
0x180007888  push    r12
0x18000788a  push    r13
0x18000788c  push    r14
0x18000788e  push    r15
0x180007890  sub     rsp, 120h
0x180007897  mov     rax, cs:__security_cookie
0x18000789e  xor     rax, rsp
0x1800078a1  mov     [rsp+158h+var_48], rax
0x1800078a9  mov     r15, r8
0x1800078ac  mov     r12, rdx
0x1800078af  mov     [rsp+158h+var_F8], rcx
0x1800078b4  mov     [rsp+158h+var_E8], rdx
0x1800078b9  xor     r10d, r10d
0x1800078bc  mov     [rsp+158h+var_108], r10d
0x1800078c1  mov     [rdx], r10
0x1800078c4  mov     [rdx+8], r10
0x1800078c8  mov     [rsp+158h+var_108], 1
0x1800078d0  lea     r14, [rcx+20h]
0x1800078d4  mov     rsi, [r14]
0x1800078d7  mov     rbx, [rsi+8]
0x1800078db  xor     eax, eax
0x1800078dd  mov     [rsp+158h+var_D4], eax
0x1800078e4  mov     ebp, 0FFFFFFFFh
0x1800078e9  cmp     [rbx+19h], al
0x1800078ec  jnz     loc_1800079AF
0x1800078f2  mov     r9, [rbx+20h]
0x1800078f6  mov     r8, [rbx+28h]
0x1800078fa  sub     r8, r9; Size
0x1800078fd  mov     rcx, [r15+8]
0x180007901  mov     rdx, [r15]; Buf2
0x180007904  mov     rax, rcx
0x180007907  sub     rax, rdx
0x18000790a  cmp     r8, rax
0x18000790d  jnb     short loc_18000797F
0x18000790f  mov     edi, ebp
0x180007911  mov     ecx, [r15+28h]
0x180007915  cmp     qword ptr [r15+30h], 7
0x18000791a  jbe     short loc_180007974
0x18000791c  mov     rax, [r15+18h]
0x180007920  lea     r8, [rbx+38h]; lpString1
0x180007924  cmp     qword ptr [r8+18h], 7
0x180007929  ja      short loc_18000797A
0x18000792b  mov     [rsp+158h+lParam], r10; lParam
0x180007930  mov     [rsp+158h+lpReserved], r10; lpReserved
0x180007935  mov     [rsp+158h+lpVersionInformation], r10; lpVersionInformation
0x18000793a  mov     [rsp+158h+cchCount2], ecx; cchCount2
0x18000793e  mov     [rsp+158h+lpString2], rax; lpString2
0x180007943  mov     r9d, [rbx+48h]; cchCount1
0x180007947  mov     edx, 1; dwCmpFlags
0x18000794c  lea     rcx, LocaleName; lpLocaleName
0x180007953  call    cs:__imp_CompareStringEx
0x180007959  mov     ecx, eax
0x18000795b  cmp     eax, 1
0x18000795e  jnz     loc_180007C09
0x180007964  mov     rbx, [rbx+10h]
0x180007968  xor     r10d, r10d
0x18000796b  cmp     [rbx+19h], r10b
0x18000796f  jmp     loc_1800078EC
0x180007974  lea     rax, [r15+18h]
0x180007978  jmp     short loc_180007920
0x18000797a  mov     r8, [r8]
0x18000797d  jmp     short loc_18000792B
0x18000797f  sub     rcx, rdx
0x180007982  cmp     r8, rcx
0x180007985  jbe     short loc_18000798E
0x180007987  mov     edi, 1
0x18000798c  jmp     short loc_180007911
0x18000798e  mov     rcx, r9; Buf1
0x180007991  call    memcmp_0
0x180007996  xor     r10d, r10d
0x180007999  test    eax, eax
0x18000799b  js      loc_180007C02
0x1800079a1  mov     edi, r10d
0x1800079a4  test    eax, eax
0x1800079a6  setnle  dil
0x1800079aa  jmp     loc_180007911
0x1800079af  cmp     byte ptr [rsi+19h], 0
0x1800079b3  jz      loc_180007A7F
0x1800079b9  mov     ecx, 0A8h; Size
0x1800079be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800079c3  mov     rdi, rax
0x1800079c6  mov     [rsp+158h+var_100], rax
0x1800079cb  xorps   xmm0, xmm0
0x1800079ce  movups  xmmword ptr [rax], xmm0
0x1800079d1  mov     dword ptr [rax+8], 1
0x1800079d8  mov     dword ptr [rax+0Ch], 1
0x1800079df  lea     rax, ??_7?$_Ref_count_obj2@VState@ApplicationStateTable@Broker@@@std@@6B@; const std::_Ref_count_obj2<Broker::ApplicationStateTable::State>::`vftable'
0x1800079e6  mov     [rdi], rax
0x1800079e9  lea     rbx, [rdi+10h]
0x1800079ed  mov     r8, [rsp+158h+var_F8]
0x1800079f2  mov     rdx, r15
0x1800079f5  mov     rcx, rbx
0x1800079f8  call    ??0State@ApplicationStateTable@Broker@@QEAA@AEBUApplicationIdentity@2@AEBV?$vector@KV?$allocator@K@std@@@std@@@Z; Broker::ApplicationStateTable::State::State(Broker::ApplicationIdentity const &,std::vector<ulong> const &)
0x1800079fd  nop
0x1800079fe  mov     [rsp+158h+var_108], 3
0x180007a06  mov     [r12], rbx
0x180007a0a  mov     rcx, [r12+8]; this
0x180007a0f  mov     [r12+8], rdi
0x180007a14  test    rcx, rcx
0x180007a17  jnz     loc_180007C36
0x180007a1d  mov     rdx, r15; struct Broker::ApplicationIdentity *
0x180007a20  lea     rcx, [rsp+158h+var_B8]; this
0x180007a28  call    ??0ApplicationIdentity@Broker@@QEAA@AEBU01@@Z; Broker::ApplicationIdentity::ApplicationIdentity(Broker::ApplicationIdentity const &)
0x180007a2d  mov     rdx, r12
0x180007a30  lea     rcx, [rsp+158h+var_60]
0x180007a38  call    ??0?$shared_ptr@VSebEvent@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(std::shared_ptr<Broker::SebEvent> const &)
0x180007a3d  mov     [rsp+158h+var_108], 7
0x180007a45  lea     r8, [rsp+158h+var_B8]
0x180007a4d  lea     rdx, [rsp+158h+var_F8]
0x180007a52  mov     rcx, r14
0x180007a55  call    ??$_Emplace@U?$pair@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@U?$less@UApplicationIdentity@Broker@@@4@V?$allocator@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::_Emplace<std::pair<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>>>(std::pair<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>> &&)
0x180007a5a  nop
0x180007a5b  mov     rcx, [rsp+158h+var_58]; this
0x180007a63  test    rcx, rcx
0x180007a66  jz      short loc_180007A6D
0x180007a68  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180007a6d  lea     rcx, [rsp+158h+var_B8]; this
0x180007a75  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180007a7a  jmp     loc_180007BA1
0x180007a7f  mov     rdx, [rsi+20h]; Buf2
0x180007a83  mov     rax, [rsi+28h]
0x180007a87  sub     rax, rdx
0x180007a8a  mov     rcx, [r15]; Buf1
0x180007a8d  mov     r8, [r15+8]
0x180007a91  sub     r8, rcx; Size
0x180007a94  cmp     r8, rax
0x180007a97  jnb     loc_180007B1F
0x180007a9d  mov     ebx, ebp
0x180007a9f  mov     ecx, [rsi+48h]
0x180007aa2  lea     rax, [rsi+38h]
0x180007aa6  cmp     qword ptr [rax+18h], 7
0x180007aab  jbe     short loc_180007AB0
0x180007aad  mov     rax, [rax]
0x180007ab0  lea     r8, [r15+18h]; lpString1
0x180007ab4  cmp     qword ptr [r8+18h], 7
0x180007ab9  ja      short loc_180007B1A
0x180007abb  mov     [rsp+158h+lParam], r10; lParam
0x180007ac0  mov     [rsp+158h+lpReserved], r10; lpReserved
0x180007ac5  mov     [rsp+158h+lpVersionInformation], r10; lpVersionInformation
0x180007aca  mov     [rsp+158h+cchCount2], ecx; cchCount2
0x180007ace  mov     [rsp+158h+lpString2], rax; lpString2
0x180007ad3  mov     r9d, [r15+28h]; cchCount1
0x180007ad7  mov     edx, 1; dwCmpFlags
0x180007adc  lea     rcx, LocaleName; lpLocaleName
0x180007ae3  call    cs:__imp_CompareStringEx
0x180007ae9  mov     ecx, eax
0x180007aeb  cmp     eax, 1
0x180007aee  jz      loc_1800079B9
0x180007af4  sub     ecx, 2
0x180007af7  jz      short loc_180007B2F
0x180007af9  cmp     ecx, 1
0x180007afc  jz      short loc_180007B37
0x180007afe  lea     rcx, [rsp+158h+pExceptionObject]; this
0x180007b03  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180007b08  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180007b0f  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x180007b14  call    _CxxThrowException_0
0x180007b1a  mov     r8, [r8]
0x180007b1d  jmp     short loc_180007ABB
0x180007b1f  jbe     loc_180007BCF
0x180007b25  mov     ebx, 1
0x180007b2a  jmp     loc_180007A9F
0x180007b2f  cmp     ebx, ebp
0x180007b31  jz      loc_1800079B9
0x180007b37  cmp     rsi, [r14]
0x180007b3a  jz      loc_1800079B9
0x180007b40  mov     rax, [rsi+80h]
0x180007b47  test    rax, rax
0x180007b4a  jz      short loc_180007B50
0x180007b4c  lock inc dword ptr [rax+8]
0x180007b50  mov     rcx, [rsi+80h]
0x180007b57  mov     rax, [rsi+78h]
0x180007b5b  mov     [r12], rax
0x180007b5f  mov     rbx, [r12+8]
0x180007b64  mov     [r12+8], rcx
0x180007b69  test    rbx, rbx
0x180007b6c  jz      short loc_180007BA1
0x180007b6e  mov     eax, ebp
0x180007b70  lock xadd [rbx+8], eax
0x180007b75  cmp     eax, 1
0x180007b78  jnz     short loc_180007BA1
0x180007b7a  mov     rax, [rbx]
0x180007b7d  mov     rcx, rbx
0x180007b80  mov     rax, [rax]
0x180007b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b88  lock xadd [rbx+0Ch], ebp
0x180007b8d  cmp     ebp, 1
0x180007b90  jnz     short loc_180007BA1
0x180007b92  mov     rax, [rbx]
0x180007b95  mov     rcx, rbx
0x180007b98  mov     rax, [rax+8]
0x180007b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ba1  mov     rax, r12
0x180007ba4  mov     rcx, [rsp+158h+var_48]
0x180007bac  xor     rcx, rsp; StackCookie
0x180007baf  call    __security_check_cookie
0x180007bb4  mov     rbx, [rsp+158h+arg_18]
0x180007bbc  add     rsp, 120h
0x180007bc3  pop     r15
0x180007bc5  pop     r14
0x180007bc7  pop     r13
0x180007bc9  pop     r12
0x180007bcb  pop     rdi
0x180007bcc  pop     rsi
0x180007bcd  pop     rbp
0x180007bce  retn
0x180007bcf  call    memcmp_0
0x180007bd4  xor     r10d, r10d
0x180007bd7  test    eax, eax
0x180007bd9  js      short loc_180007C2F
0x180007bdb  mov     ebx, r10d
0x180007bde  test    eax, eax
0x180007be0  setnle  bl
0x180007be3  jmp     loc_180007A9F
0x180007be8  cmp     edi, ebp
0x180007bea  jz      loc_180007964
0x180007bf0  mov     rsi, rbx
0x180007bf3  mov     rbx, [rbx]
0x180007bf6  xor     r10d, r10d
0x180007bf9  cmp     [rbx+19h], r10b
0x180007bfd  jmp     loc_1800078EC
0x180007c02  mov     edi, ebp
0x180007c04  jmp     loc_180007911
0x180007c09  sub     ecx, 2
0x180007c0c  jz      short loc_180007BE8
0x180007c0e  cmp     ecx, 1
0x180007c11  jz      short loc_180007BF0
0x180007c13  lea     rcx, [rsp+158h+pExceptionObject]; this
0x180007c18  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180007c1d  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180007c24  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x180007c29  call    _CxxThrowException_0
0x180007c2f  mov     ebx, ebp
0x180007c31  jmp     loc_180007A9F
0x180007c36  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180007c3b  jmp     loc_180007A1D
```
