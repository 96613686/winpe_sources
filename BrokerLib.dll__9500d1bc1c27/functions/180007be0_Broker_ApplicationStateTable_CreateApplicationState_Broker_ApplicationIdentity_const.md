# Broker::ApplicationStateTable::CreateApplicationState(Broker::ApplicationIdentity const &)

- ea: `0x180007be0`
- end: `0x180008006`
- name: `?CreateApplicationState@ApplicationStateTable@Broker@@QEAA?AV?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@AEBUApplicationIdentity@2@@Z`
- size: `1062`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180007a0c`
- `0x180017308`

## callees

- `0x180004ae0`
- `0x180004d70`
- `0x180006eb0`
- `0x180007be0`
- `0x18000800c`
- `0x180013018`
- `0x180014a40`
- `0x180015af0`
- `0x180015b14`
- `0x18001659e`
- `0x1800165da`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180007cea`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180007da5`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180007cea`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180007da5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall Broker::ApplicationStateTable::CreateApplicationState(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 **v5; // r14
  __int64 *v6; // rbp
  __int64 *v7; // rbx
  size_t v8; // r8
  const void *v9; // rdx
  int v10; // eax
  int v11; // edi
  const WCHAR *lpString2; // rcx
  const WCHAR *v13; // r8
  int v14; // ecx
  const void *v15; // rdx
  size_t v16; // rax
  size_t v17; // r8
  int v18; // eax
  int v19; // ebx
  const WCHAR *v20; // rax
  const WCHAR *v21; // r8
  int v22; // ecx
  std::_Ref_count_base *v23; // rcx
  __int64 v24; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  volatile signed __int32 *v28; // rbx
  int v29; // ecx
  int v30; // ecx
  _DWORD *v31; // [rsp+58h] [rbp-100h]
  _QWORD v32[3]; // [rsp+60h] [rbp-F8h] BYREF
  _BYTE pExceptionObject[12]; // [rsp+78h] [rbp-E0h] BYREF
  int v34; // [rsp+84h] [rbp-D4h]
  _BYTE v35[88]; // [rsp+A0h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+F8h] [rbp-60h]
  std::_Ref_count_base *v37; // [rsp+100h] [rbp-58h]

  v32[0] = a1;
  v32[2] = a2;
  *a2 = 0;
  a2[1] = 0;
  v5 = (__int64 **)(a1 + 32);
  v6 = *(__int64 **)(a1 + 32);
  v7 = (__int64 *)v6[1];
  v34 = 0;
  while ( !*((_BYTE *)v7 + 25) )
  {
    v8 = v7[5] - v7[4];
    v9 = *(const void **)a3;
    if ( v8 < *(_QWORD *)(a3 + 8) - *(_QWORD *)a3 )
    {
      v11 = -1;
    }
    else if ( v8 > *(_QWORD *)(a3 + 8) - (_QWORD)v9 )
    {
      v11 = 1;
    }
    else
    {
      v10 = memcmp_0((const void *)v7[4], v9, v8);
      if ( v10 < 0 )
        v11 = -1;
      else
        v11 = v10 > 0;
    }
    if ( *(_QWORD *)(a3 + 48) <= 7u )
      lpString2 = (const WCHAR *)(a3 + 24);
    else
      lpString2 = *(const WCHAR **)(a3 + 24);
    v13 = (const WCHAR *)(v7 + 7);
    if ( (unsigned __int64)v7[10] > 7 )
      v13 = *(const WCHAR **)v13;
    v14 = CompareStringEx(&LocaleName, 1u, v13, *((_DWORD *)v7 + 18), lpString2, *(_DWORD *)(a3 + 40), 0, 0, 0);
    if ( v14 != 1 )
    {
      v29 = v14 - 2;
      if ( v29 )
      {
        if ( v29 != 1 )
        {
          Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
          throw (Broker::Win32Error *)pExceptionObject;
        }
LABEL_43:
        v6 = v7;
        v7 = (__int64 *)*v7;
        continue;
      }
      if ( v11 != -1 )
        goto LABEL_43;
    }
    v7 = (__int64 *)v7[2];
  }
  if ( *((_BYTE *)v6 + 25) )
    goto LABEL_25;
  v15 = (const void *)v6[4];
  v16 = v6[5] - (_QWORD)v15;
  v17 = *(_QWORD *)(a3 + 8) - *(_QWORD *)a3;
  if ( v17 < v16 )
  {
    v19 = -1;
  }
  else if ( v17 > v16 )
  {
    v19 = 1;
  }
  else
  {
    v18 = memcmp_0(*(const void **)a3, v15, v17);
    if ( v18 < 0 )
      v19 = -1;
    else
      v19 = v18 > 0;
  }
  v20 = (const WCHAR *)(v6 + 7);
  if ( (unsigned __int64)v6[10] > 7 )
    v20 = *(const WCHAR **)v20;
  v21 = (const WCHAR *)(a3 + 24);
  if ( *(_QWORD *)(a3 + 48) > 7u )
    v21 = *(const WCHAR **)v21;
  v22 = CompareStringEx(&LocaleName, 1u, v21, *(_DWORD *)(a3 + 40), v20, *((_DWORD *)v6 + 18), 0, 0, 0);
  if ( v22 == 1 )
    goto LABEL_25;
  v30 = v22 - 2;
  if ( v30 )
  {
    if ( v30 != 1 )
    {
      Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
      throw (Broker::Win32Error *)pExceptionObject;
    }
  }
  else if ( v19 == -1 )
  {
LABEL_25:
    v31 = operator new(0xA8u);
    *(_OWORD *)v31 = 0;
    v31[2] = 1;
    v31[3] = 1;
    *(_QWORD *)v31 = &std::_Ref_count_obj2<Broker::ApplicationStateTable::State>::`vftable';
    Broker::ApplicationStateTable::State::State(v31 + 4, a3, v32[0]);
    *a2 = (__int64)(v31 + 4);
    v23 = (std::_Ref_count_base *)a2[1];
    a2[1] = (__int64)v31;
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
    Broker::ApplicationIdentity::ApplicationIdentity(
      (Broker::ApplicationIdentity *)v35,
      (const struct Broker::ApplicationIdentity *)a3);
    v36 = 0;
    v37 = 0;
    v24 = a2[1];
    if ( v24 )
      _InterlockedIncrement((volatile signed __int32 *)(v24 + 8));
    v36 = *a2;
    v37 = (std::_Ref_count_base *)a2[1];
    std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::_Emplace<std::pair<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>>>(
      v5,
      v32,
      v35);
    if ( v37 )
      std::_Ref_count_base::_Decref(v37);
    Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v35);
    return a2;
  }
  if ( v6 == *v5 )
    goto LABEL_25;
  v26 = v6[16];
  if ( v26 )
    _InterlockedIncrement((volatile signed __int32 *)(v26 + 8));
  v27 = v6[16];
  *a2 = v6[15];
  v28 = (volatile signed __int32 *)a2[1];
  a2[1] = v27;
  if ( v28 )
  {
    if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
      if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180007be0  mov     [rsp+arg_18], rbx
0x180007be5  push    rbp
0x180007be6  push    rsi
0x180007be7  push    rdi
0x180007be8  push    r12
0x180007bea  push    r13
0x180007bec  push    r14
0x180007bee  push    r15
0x180007bf0  sub     rsp, 120h
0x180007bf7  mov     rax, cs:__security_cookie
0x180007bfe  xor     rax, rsp
0x180007c01  mov     [rsp+158h+var_48], rax
0x180007c09  mov     rsi, r8
0x180007c0c  mov     r12, rdx
0x180007c0f  mov     [rsp+158h+var_F8], rcx
0x180007c14  mov     [rsp+158h+var_E8], rdx
0x180007c19  xor     r10d, r10d
0x180007c1c  mov     [rsp+158h+var_108], r10d
0x180007c21  mov     [rdx], r10
0x180007c24  mov     [rdx+8], r10
0x180007c28  mov     [rsp+158h+var_108], 1
0x180007c30  lea     r14, [rcx+20h]
0x180007c34  mov     rbp, [r14]
0x180007c37  mov     rbx, [rbp+8]
0x180007c3b  xor     eax, eax
0x180007c3d  mov     [rsp+158h+var_D4], eax
0x180007c44  mov     r13d, 0FFFFFFFFh
0x180007c4a  cmp     [rbx+19h], al
0x180007c4d  jnz     loc_180007D18
0x180007c53  nop     dword ptr [rax+00h]
0x180007c57  nop     word ptr [rax+rax+00000000h]
0x180007c60  mov     r9, [rbx+20h]
0x180007c64  mov     r8, [rbx+28h]
0x180007c68  sub     r8, r9; Size
0x180007c6b  mov     rcx, [rsi+8]
0x180007c6f  mov     rdx, [rsi]; Buf2
0x180007c72  mov     rax, rcx
0x180007c75  sub     rax, rdx
0x180007c78  cmp     r8, rax
0x180007c7b  jb      loc_180007EA0
0x180007c81  sub     rcx, rdx
0x180007c84  cmp     r8, rcx
0x180007c87  ja      loc_180007F22
0x180007c8d  mov     rcx, r9; Buf1
0x180007c90  call    memcmp_0
0x180007c95  xor     r10d, r10d
0x180007c98  test    eax, eax
0x180007c9a  js      loc_180007EB0
0x180007ca0  mov     edi, r10d
0x180007ca3  test    eax, eax
0x180007ca5  setnle  dil
0x180007ca9  mov     eax, [rsi+28h]
0x180007cac  cmp     qword ptr [rsi+30h], 7
0x180007cb1  jbe     short loc_180007D0D
0x180007cb3  mov     rcx, [rsi+18h]
0x180007cb7  lea     r8, [rbx+38h]; lpString1
0x180007cbb  cmp     qword ptr [r8+18h], 7
0x180007cc0  ja      short loc_180007D13
0x180007cc2  mov     [rsp+158h+lParam], r10; lParam
0x180007cc7  mov     [rsp+158h+lpReserved], r10; lpReserved
0x180007ccc  mov     [rsp+158h+lpVersionInformation], r10; lpVersionInformation
0x180007cd1  mov     [rsp+158h+cchCount2], eax; cchCount2
0x180007cd5  mov     [rsp+158h+lpString2], rcx; lpString2
0x180007cda  mov     r9d, [rbx+48h]; cchCount1
0x180007cde  mov     edx, 1; dwCmpFlags
0x180007ce3  lea     rcx, LocaleName; lpLocaleName
0x180007cea  call    cs:__imp_CompareStringEx
0x180007cf0  mov     ecx, eax
0x180007cf2  cmp     eax, 1
0x180007cf5  jnz     loc_180007FA7
0x180007cfb  mov     rbx, [rbx+10h]
0x180007cff  cmp     byte ptr [rbx+19h], 0
0x180007d03  jnz     short loc_180007D18
0x180007d05  xor     r10d, r10d
0x180007d08  jmp     loc_180007C60
0x180007d0d  lea     rcx, [rsi+18h]
0x180007d11  jmp     short loc_180007CB7
0x180007d13  mov     r8, [r8]
0x180007d16  jmp     short loc_180007CC2
0x180007d18  cmp     byte ptr [rbp+19h], 0
0x180007d1c  jnz     loc_180007EA8
0x180007d22  mov     rdx, [rbp+20h]; Buf2
0x180007d26  mov     rax, [rbp+28h]
0x180007d2a  sub     rax, rdx
0x180007d2d  mov     rcx, [rsi]; Buf1
0x180007d30  mov     r8, [rsi+8]
0x180007d34  sub     r8, rcx; Size
0x180007d37  cmp     r8, rax
0x180007d3a  jb      loc_180007F0F
0x180007d40  ja      loc_180007F2C
0x180007d46  call    memcmp_0
0x180007d4b  xor     r15d, r15d
0x180007d4e  test    eax, eax
0x180007d50  js      loc_180007F1A
0x180007d56  mov     ebx, r15d
0x180007d59  test    eax, eax
0x180007d5b  setnle  bl
0x180007d5e  mov     ecx, [rbp+48h]
0x180007d61  lea     rax, [rbp+38h]
0x180007d65  cmp     qword ptr [rax+18h], 7
0x180007d6a  jbe     short loc_180007D6F
0x180007d6c  mov     rax, [rax]
0x180007d6f  mov     r9d, [rsi+28h]; cchCount1
0x180007d73  lea     r8, [rsi+18h]
0x180007d77  cmp     qword ptr [r8+18h], 7
0x180007d7c  jbe     short loc_180007D81
0x180007d7e  mov     r8, [r8]; lpString1
0x180007d81  mov     [rsp+158h+lParam], r15; lParam
0x180007d86  mov     [rsp+158h+lpReserved], r15; lpReserved
0x180007d8b  mov     [rsp+158h+lpVersionInformation], r15; lpVersionInformation
0x180007d90  mov     [rsp+158h+cchCount2], ecx; cchCount2
0x180007d94  mov     [rsp+158h+lpString2], rax; lpString2
0x180007d99  mov     edx, 1; dwCmpFlags
0x180007d9e  lea     rcx, LocaleName; lpLocaleName
0x180007da5  call    cs:__imp_CompareStringEx
0x180007dab  mov     ecx, eax
0x180007dad  cmp     eax, 1
0x180007db0  jnz     loc_180007FCD
0x180007db6  mov     ecx, 0A8h; Size
0x180007dbb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007dc0  mov     rdi, rax
0x180007dc3  mov     [rsp+158h+var_100], rax
0x180007dc8  xorps   xmm0, xmm0
0x180007dcb  movups  xmmword ptr [rax], xmm0
0x180007dce  mov     dword ptr [rax+8], 1
0x180007dd5  mov     dword ptr [rax+0Ch], 1
0x180007ddc  lea     rax, ??_7?$_Ref_count_obj2@VState@ApplicationStateTable@Broker@@@std@@6B@; const std::_Ref_count_obj2<Broker::ApplicationStateTable::State>::`vftable'
0x180007de3  mov     [rdi], rax
0x180007de6  lea     rbx, [rdi+10h]
0x180007dea  mov     r8, [rsp+158h+var_F8]
0x180007def  mov     rdx, rsi
0x180007df2  mov     rcx, rbx
0x180007df5  call    ??0State@ApplicationStateTable@Broker@@QEAA@AEBUApplicationIdentity@2@AEBV?$vector@KV?$allocator@K@std@@@std@@@Z; Broker::ApplicationStateTable::State::State(Broker::ApplicationIdentity const &,std::vector<ulong> const &)
0x180007dfa  nop
0x180007dfb  mov     [rsp+158h+var_108], 3
0x180007e03  mov     [r12], rbx
0x180007e07  mov     rcx, [r12+8]; this
0x180007e0c  mov     [r12+8], rdi
0x180007e11  test    rcx, rcx
0x180007e14  jnz     loc_180007FFB
0x180007e1a  mov     rdx, rsi; struct Broker::ApplicationIdentity *
0x180007e1d  lea     rcx, [rsp+158h+var_B8]; this
0x180007e25  call    ??0ApplicationIdentity@Broker@@QEAA@AEBU01@@Z; Broker::ApplicationIdentity::ApplicationIdentity(Broker::ApplicationIdentity const &)
0x180007e2a  mov     [rsp+158h+var_60], r15
0x180007e32  mov     [rsp+158h+var_58], r15
0x180007e3a  mov     rax, [r12+8]
0x180007e3f  test    rax, rax
0x180007e42  jz      short loc_180007E48
0x180007e44  lock inc dword ptr [rax+8]
0x180007e48  mov     rax, [r12]
0x180007e4c  mov     [rsp+158h+var_60], rax
0x180007e54  mov     rax, [r12+8]
0x180007e59  mov     [rsp+158h+var_58], rax
0x180007e61  mov     [rsp+158h+var_108], 7
0x180007e69  lea     r8, [rsp+158h+var_B8]
0x180007e71  lea     rdx, [rsp+158h+var_F8]
0x180007e76  mov     rcx, r14
0x180007e79  call    ??$_Emplace@U?$pair@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@U?$less@UApplicationIdentity@Broker@@@4@V?$allocator@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::_Emplace<std::pair<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>>>(std::pair<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>> &&)
0x180007e7e  nop
0x180007e7f  mov     rcx, [rsp+158h+var_58]; this
0x180007e87  test    rcx, rcx
0x180007e8a  jz      short loc_180007E91
0x180007e8c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180007e91  lea     rcx, [rsp+158h+var_B8]; this
0x180007e99  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180007e9e  jmp     short loc_180007EE1
0x180007ea0  mov     edi, r13d
0x180007ea3  jmp     loc_180007CA9
0x180007ea8  xor     r15d, r15d
0x180007eab  jmp     loc_180007DB6
0x180007eb0  mov     edi, r13d
0x180007eb3  jmp     loc_180007CA9
0x180007eb8  mov     rax, [rbx]
0x180007ebb  mov     rcx, rbx
0x180007ebe  mov     rax, [rax]
0x180007ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ec6  lock xadd [rbx+0Ch], r13d
0x180007ecc  cmp     r13d, 1
0x180007ed0  jnz     short loc_180007EE1
0x180007ed2  mov     rax, [rbx]
0x180007ed5  mov     rcx, rbx
0x180007ed8  mov     rax, [rax+8]
0x180007edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ee1  mov     rax, r12
0x180007ee4  mov     rcx, [rsp+158h+var_48]
0x180007eec  xor     rcx, rsp; StackCookie
0x180007eef  call    __security_check_cookie
0x180007ef4  mov     rbx, [rsp+158h+arg_18]
0x180007efc  add     rsp, 120h
0x180007f03  pop     r15
0x180007f05  pop     r14
0x180007f07  pop     r13
0x180007f09  pop     r12
0x180007f0b  pop     rdi
0x180007f0c  pop     rsi
0x180007f0d  pop     rbp
0x180007f0e  retn
0x180007f0f  mov     ebx, r13d
0x180007f12  xor     r15d, r15d
0x180007f15  jmp     loc_180007D5E
0x180007f1a  mov     ebx, r13d
0x180007f1d  jmp     loc_180007D5E
0x180007f22  mov     edi, 1
0x180007f27  jmp     loc_180007CA9
0x180007f2c  mov     ebx, 1
0x180007f31  xor     r15d, r15d
0x180007f34  jmp     loc_180007D5E
0x180007f39  cmp     edi, r13d
0x180007f3c  jz      loc_180007CFB
0x180007f42  mov     rbp, rbx
0x180007f45  mov     rbx, [rbx]
0x180007f48  jmp     loc_180007CFF
0x180007f4d  cmp     ebx, r13d
0x180007f50  jz      loc_180007DB6
0x180007f56  cmp     rbp, [r14]
0x180007f59  jz      loc_180007DB6
0x180007f5f  mov     rax, [rbp+80h]
0x180007f66  test    rax, rax
0x180007f69  jz      short loc_180007F6F
0x180007f6b  lock inc dword ptr [rax+8]
0x180007f6f  mov     rcx, [rbp+80h]
0x180007f76  mov     rax, [rbp+78h]
0x180007f7a  mov     [r12], rax
0x180007f7e  mov     rbx, [r12+8]
0x180007f83  mov     [r12+8], rcx
0x180007f88  test    rbx, rbx
0x180007f8b  jz      loc_180007EE1
0x180007f91  mov     eax, r13d
0x180007f94  lock xadd [rbx+8], eax
0x180007f99  cmp     eax, 1
0x180007f9c  jz      loc_180007EB8
0x180007fa2  jmp     loc_180007EE1
0x180007fa7  sub     ecx, 2
0x180007faa  jz      short loc_180007F39
0x180007fac  cmp     ecx, 1
0x180007faf  jz      short loc_180007F42
0x180007fb1  lea     rcx, [rsp+158h+pExceptionObject]; this
0x180007fb6  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180007fbb  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180007fc2  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x180007fc7  call    _CxxThrowException_0
0x180007fcd  sub     ecx, 2
0x180007fd0  jz      loc_180007F4D
0x180007fd6  cmp     ecx, 1
0x180007fd9  jz      loc_180007F56
0x180007fdf  lea     rcx, [rsp+158h+pExceptionObject]; this
0x180007fe4  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180007fe9  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180007ff0  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x180007ff5  call    _CxxThrowException_0
0x180007ffb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180008000  jmp     loc_180007E1A
```
