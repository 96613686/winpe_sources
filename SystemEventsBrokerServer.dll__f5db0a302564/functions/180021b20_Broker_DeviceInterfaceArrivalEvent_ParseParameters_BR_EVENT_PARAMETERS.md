# Broker::DeviceInterfaceArrivalEvent::ParseParameters(_BR_EVENT_PARAMETERS *)

- ea: `0x180021b20`
- end: `0x180021e85`
- name: `?ParseParameters@DeviceInterfaceArrivalEvent@Broker@@UEAAXPEAU_BR_EVENT_PARAMETERS@@@Z`
- size: `869`
- prototype: `void __fastcall(Broker::DeviceInterfaceArrivalEvent *__hidden this, struct _BR_EVENT_PARAMETERS *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180014d20`
- `0x180019fa4`
- `0x18001a1f4`
- `0x18001cf50`
- `0x18001d9ac`
- `0x180021b20`
- `0x180022440`

## import_xrefs

- `ntdll!RtlGUIDFromString` at `0x180021c70`
- `ntdll!RtlGUIDFromString` at `0x180021c70`
- `ntdll!RtlInitUnicodeString` at `0x180021c62`
- `ntdll!RtlInitUnicodeString` at `0x180021c62`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021b95`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021c0a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021cc8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021b95`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021c0a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021cc8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Broker::DeviceInterfaceArrivalEvent::ParseParameters(
        Broker::DeviceInterfaceArrivalEvent *this,
        struct _BR_EVENT_PARAMETERS *a2)
{
  unsigned __int64 v4; // r13
  unsigned int i; // r12d
  __int64 v6; // rbx
  int v7; // eax
  __int64 v8; // r8
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r15
  __int64 v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rax
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-39h] BYREF
  int v17; // [rsp+48h] [rbp-21h]
  _BYTE v18[8]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v19[8]; // [rsp+58h] [rbp-11h] BYREF
  void **v20; // [rsp+60h] [rbp-9h] BYREF
  __int128 v21; // [rsp+68h] [rbp-1h]
  int v22; // [rsp+78h] [rbp+Fh]

  v4 = 0;
  for ( i = 0; i < *(unsigned __int16 *)a2; ++i )
  {
    v6 = 32LL * i;
    v7 = CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v6 + *((_QWORD *)a2 + 1)), -1, L"Type", -1);
    v8 = *((_QWORD *)a2 + 1);
    if ( v7 == 2 )
    {
      if ( *(_DWORD *)(v6 + v8 + 8) )
      {
        *(_OWORD *)&pExceptionObject[8] = 0;
        v17 = 4;
        *(_QWORD *)pExceptionObject = &Broker::InvalidParameter::`vftable';
        throw (Broker::InvalidParameter *)pExceptionObject;
      }
      if ( *(_DWORD *)(v6 + v8 + 16) != *((_DWORD *)this + 2) )
      {
        *(_OWORD *)&pExceptionObject[8] = 0;
        v17 = 4;
        *(_QWORD *)pExceptionObject = &Broker::InvalidParameter::`vftable';
        throw (Broker::InvalidParameter *)pExceptionObject;
      }
    }
    else
    {
      v9 = CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v6 + v8), -1, L"DeviceInterfaceClass", -1);
      v10 = *((_QWORD *)a2 + 1);
      if ( v9 == 2 )
      {
        if ( *(_DWORD *)(v6 + v10 + 8) == 2 )
        {
          *(_OWORD *)pExceptionObject = 0;
          RtlInitUnicodeString((PUNICODE_STRING)pExceptionObject, *(PCWSTR *)(v6 + v10 + 16));
          if ( RtlGUIDFromString((PUNICODE_STRING)pExceptionObject, (GUID *)((char *)this + 40)) < 0 )
          {
            v21 = 0;
            v22 = 4;
            v20 = &Broker::InvalidParameter::`vftable';
            throw (Broker::InvalidParameter *)&v20;
          }
        }
        else
        {
          if ( *(_DWORD *)(v6 + v10 + 8) != 4 )
          {
            *(_OWORD *)&pExceptionObject[8] = 0;
            v17 = 4;
            *(_QWORD *)pExceptionObject = &Broker::InvalidParameter::`vftable';
            throw (Broker::InvalidParameter *)pExceptionObject;
          }
          if ( *(_WORD *)(v6 + v10 + 16) != 16 )
          {
            *(_OWORD *)&pExceptionObject[8] = 0;
            v17 = 4;
            *(_QWORD *)pExceptionObject = &Broker::InvalidParameter::`vftable';
            throw (Broker::InvalidParameter *)pExceptionObject;
          }
          memcpy_0((char *)this + 40, *(const void **)(v6 + v10 + 24), *(unsigned __int16 *)(v6 + v10 + 16));
        }
      }
      else
      {
        if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v6 + v10), -1, L"HWID", -1) != 2 )
        {
          v21 = 0;
          v22 = 4;
          v20 = &Broker::InvalidParameter::`vftable';
          throw (Broker::InvalidParameter *)&v20;
        }
        v11 = *((_QWORD *)a2 + 1);
        if ( *(_DWORD *)(v6 + v11 + 8) == 2 )
        {
          v15 = std::wstring::wstring(&v20, *(_QWORD *)(v6 + v11 + 16));
          std::vector<std::wstring>::emplace<std::wstring>((char *)this + 56, v19, *((_QWORD *)this + 8), v15);
          std::wstring::~wstring((__int64)&v20);
        }
        else
        {
          if ( *(_DWORD *)(v6 + v11 + 8) != 3 )
          {
            v21 = 0;
            v22 = 4;
            v20 = &Broker::InvalidParameter::`vftable';
            throw (Broker::InvalidParameter *)&v20;
          }
          v12 = *(_QWORD *)(v6 + v11 + 24);
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)(v12 + 2 * v13) );
          while ( v13 && v4 < *(unsigned __int16 *)(v6 + *((_QWORD *)a2 + 1) + 16) )
          {
            v14 = std::wstring::wstring(&v20, v12);
            std::vector<std::wstring>::emplace<std::wstring>((char *)this + 56, v18, *((_QWORD *)this + 8), v14);
            std::wstring::~wstring((__int64)&v20);
            v4 += v13 + 1;
            v12 += 2 * v13 + 2;
            v13 = -1;
            do
              ++v13;
            while ( *(_WORD *)(v12 + 2 * v13) );
          }
          v4 = 0;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180021b20  mov     [rsp-8+arg_10], rbx
0x180021b25  push    rbp
0x180021b26  push    rsi
0x180021b27  push    rdi
0x180021b28  push    r12
0x180021b2a  push    r13
0x180021b2c  push    r14
0x180021b2e  push    r15
0x180021b30  lea     rbp, [rsp-27h]
0x180021b35  sub     rsp, 90h
0x180021b3c  mov     rax, cs:__security_cookie
0x180021b43  xor     rax, rsp
0x180021b46  mov     [rbp+57h+var_40], rax
0x180021b4a  mov     r14, rdx
0x180021b4d  mov     rsi, rcx
0x180021b50  xor     r13d, r13d
0x180021b53  mov     r12d, r13d
0x180021b56  lea     edi, [r13+4]
0x180021b5a  movzx   eax, word ptr [r14]
0x180021b5e  cmp     r12d, eax
0x180021b61  jnb     loc_180021E5E
0x180021b67  mov     ebx, r12d
0x180021b6a  shl     rbx, 5
0x180021b6e  mov     r8, [r14+8]
0x180021b72  mov     [rsp+0C0h+cchCount2], 0FFFFFFFFh; cchCount2
0x180021b7a  lea     rax, aType_2; "Type"
0x180021b81  mov     [rsp+0C0h+lpString2], rax; lpString2
0x180021b86  or      r9d, 0FFFFFFFFh; cchCount1
0x180021b8a  mov     r8, [rbx+r8]; lpString1
0x180021b8e  lea     edx, [r9+2]; dwCmpFlags
0x180021b92  lea     ecx, [rdx+7Eh]; Locale
0x180021b95  call    cs:__imp_CompareStringW
0x180021b9b  mov     r8, [r14+8]
0x180021b9f  cmp     eax, 2
0x180021ba2  jnz     short loc_180021BE3
0x180021ba4  cmp     [rbx+r8+8], r13d
0x180021ba9  jnz     loc_180021DA0
0x180021baf  mov     eax, [rsi+8]
0x180021bb2  cmp     [rbx+r8+10h], eax
0x180021bb7  jz      loc_180021D69
0x180021bbd  xorps   xmm0, xmm0
0x180021bc0  movups  xmmword ptr [rbp+57h+pExceptionObject+8], xmm0
0x180021bc4  mov     [rbp+57h+var_78], edi
0x180021bc7  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180021bce  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x180021bd2  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180021bd9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180021bdd  call    _CxxThrowException_0
0x180021be3  mov     [rsp+0C0h+cchCount2], 0FFFFFFFFh; cchCount2
0x180021beb  lea     rax, aDeviceinterfac; "DeviceInterfaceClass"
0x180021bf2  mov     [rsp+0C0h+lpString2], rax; lpString2
0x180021bf7  or      r9d, 0FFFFFFFFh; cchCount1
0x180021bfb  mov     r8, [rbx+r8]; lpString1
0x180021bff  lea     r15d, [r9+2]
0x180021c03  mov     edx, r15d; dwCmpFlags
0x180021c06  lea     ecx, [r15+7Eh]; Locale
0x180021c0a  call    cs:__imp_CompareStringW
0x180021c10  mov     rdx, [r14+8]
0x180021c14  cmp     eax, 2
0x180021c17  jnz     loc_180021CA4
0x180021c1d  cmp     [rbx+rdx+8], eax
0x180021c21  jz      short loc_180021C52
0x180021c23  cmp     [rbx+rdx+8], edi
0x180021c27  jnz     loc_180021DEC
0x180021c2d  cmp     word ptr [rbx+rdx+10h], 10h
0x180021c33  jnz     loc_180021DC6
0x180021c39  movzx   r8d, word ptr [rbx+rdx+10h]; Size
0x180021c3f  lea     rcx, [rsi+28h]; void *
0x180021c43  mov     rdx, [rbx+rdx+18h]; Src
0x180021c48  call    memcpy_0
0x180021c4d  jmp     loc_180021D69
0x180021c52  xorps   xmm0, xmm0
0x180021c55  movups  xmmword ptr [rbp+57h+pExceptionObject], xmm0
0x180021c59  mov     rdx, [rbx+rdx+10h]; SourceString
0x180021c5e  lea     rcx, [rbp+57h+pExceptionObject]; DestinationString
0x180021c62  call    cs:__imp_RtlInitUnicodeString
0x180021c68  lea     rdx, [rsi+28h]; Guid
0x180021c6c  lea     rcx, [rbp+57h+pExceptionObject]; GuidString
0x180021c70  call    cs:__imp_RtlGUIDFromString
0x180021c76  test    eax, eax
0x180021c78  jns     loc_180021D69
0x180021c7e  xorps   xmm0, xmm0
0x180021c81  movups  [rbp+57h+var_58], xmm0
0x180021c85  mov     [rbp+57h+var_48], edi
0x180021c88  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180021c8f  mov     [rbp+57h+var_60], rax
0x180021c93  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180021c9a  lea     rcx, [rbp+57h+var_60]; pExceptionObject
0x180021c9e  call    _CxxThrowException_0
0x180021ca4  mov     [rsp+0C0h+cchCount2], 0FFFFFFFFh; cchCount2
0x180021cac  lea     rax, aHwid; "HWID"
0x180021cb3  mov     [rsp+0C0h+lpString2], rax; lpString2
0x180021cb8  or      r9d, 0FFFFFFFFh; cchCount1
0x180021cbc  mov     r8, [rbx+rdx]; lpString1
0x180021cc0  mov     edx, r15d; dwCmpFlags
0x180021cc3  mov     ecx, 7Fh; Locale
0x180021cc8  call    cs:__imp_CompareStringW
0x180021cce  cmp     eax, 2
0x180021cd1  jnz     loc_180021E38
0x180021cd7  mov     rdx, [r14+8]
0x180021cdb  mov     ecx, [rbx+rdx+8]
0x180021cdf  sub     ecx, eax
0x180021ce1  jz      loc_180021D71
0x180021ce7  cmp     ecx, r15d
0x180021cea  jnz     loc_180021E12
0x180021cf0  mov     r15, [rbx+rdx+18h]
0x180021cf5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180021cf9  inc     rdi
0x180021cfc  cmp     [r15+rdi*2], r13w
0x180021d01  jnz     short loc_180021CF9
0x180021d03  jmp     short loc_180021D5C
0x180021d05  mov     rax, [r14+8]
0x180021d09  movzx   ecx, word ptr [rbx+rax+10h]
0x180021d0e  cmp     r13, rcx
0x180021d11  jnb     short loc_180021D61
0x180021d13  mov     rdx, r15
0x180021d16  lea     rcx, [rbp+57h+var_60]
0x180021d1a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180021d1f  nop
0x180021d20  lea     rcx, [rsi+38h]
0x180021d24  mov     r9, rax
0x180021d27  mov     r8, [rsi+40h]
0x180021d2b  lea     rdx, [rbp+57h+var_70]
0x180021d2f  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::vector<std::wstring>::emplace<std::wstring>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring &&)
0x180021d34  nop
0x180021d35  lea     rcx, [rbp+57h+var_60]
0x180021d39  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021d3e  inc     r13
0x180021d41  add     r13, rdi
0x180021d44  lea     r15, [r15+rdi*2]
0x180021d48  add     r15, 2
0x180021d4c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180021d50  xor     eax, eax
0x180021d52  inc     rdi
0x180021d55  cmp     [r15+rdi*2], ax
0x180021d5a  jnz     short loc_180021D52
0x180021d5c  test    rdi, rdi
0x180021d5f  jnz     short loc_180021D05
0x180021d61  mov     edi, 4
0x180021d66  xor     r13d, r13d
0x180021d69  inc     r12d
0x180021d6c  jmp     loc_180021B5A
0x180021d71  mov     rdx, [rbx+rdx+10h]
0x180021d76  lea     rcx, [rbp+57h+var_60]
0x180021d7a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180021d7f  nop
0x180021d80  lea     rcx, [rsi+38h]
0x180021d84  mov     r9, rax
0x180021d87  mov     r8, [rsi+40h]
0x180021d8b  lea     rdx, [rbp+57h+var_68]
0x180021d8f  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::vector<std::wstring>::emplace<std::wstring>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring &&)
0x180021d94  nop
0x180021d95  lea     rcx, [rbp+57h+var_60]
0x180021d99  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021d9e  jmp     short loc_180021D69
0x180021da0  xorps   xmm0, xmm0
0x180021da3  movups  xmmword ptr [rbp+57h+pExceptionObject+8], xmm0
0x180021da7  mov     [rbp+57h+var_78], edi
0x180021daa  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180021db1  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x180021db5  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180021dbc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180021dc0  call    _CxxThrowException_0
0x180021dc6  xorps   xmm0, xmm0
0x180021dc9  movups  xmmword ptr [rbp+57h+pExceptionObject+8], xmm0
0x180021dcd  mov     [rbp+57h+var_78], edi
0x180021dd0  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180021dd7  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x180021ddb  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180021de2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180021de6  call    _CxxThrowException_0
0x180021dec  xorps   xmm0, xmm0
0x180021def  movups  xmmword ptr [rbp+57h+pExceptionObject+8], xmm0
0x180021df3  mov     [rbp+57h+var_78], edi
0x180021df6  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180021dfd  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x180021e01  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180021e08  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180021e0c  call    _CxxThrowException_0
0x180021e12  xorps   xmm0, xmm0
0x180021e15  movups  [rbp+57h+var_58], xmm0
0x180021e19  mov     [rbp+57h+var_48], edi
0x180021e1c  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180021e23  mov     [rbp+57h+var_60], rax
0x180021e27  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180021e2e  lea     rcx, [rbp+57h+var_60]; pExceptionObject
0x180021e32  call    _CxxThrowException_0
0x180021e38  xorps   xmm0, xmm0
0x180021e3b  movups  [rbp+57h+var_58], xmm0
0x180021e3f  mov     [rbp+57h+var_48], edi
0x180021e42  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180021e49  mov     [rbp+57h+var_60], rax
0x180021e4d  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180021e54  lea     rcx, [rbp+57h+var_60]; pExceptionObject
0x180021e58  call    _CxxThrowException_0
0x180021e5e  mov     rcx, [rbp+57h+var_40]
0x180021e62  xor     rcx, rsp; StackCookie
0x180021e65  call    __security_check_cookie
0x180021e6a  mov     rbx, [rsp+0C0h+arg_10]
0x180021e72  add     rsp, 90h
0x180021e79  pop     r15
0x180021e7b  pop     r14
0x180021e7d  pop     r13
0x180021e7f  pop     r12
0x180021e81  pop     rdi
0x180021e82  pop     rsi
0x180021e83  pop     rbp
0x180021e84  retn
```
