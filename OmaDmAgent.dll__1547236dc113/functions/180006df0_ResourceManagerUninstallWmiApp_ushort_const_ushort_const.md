# ResourceManagerUninstallWmiApp(ushort const *,ushort const *)

- ea: `0x180006df0`
- end: `0x180006fb2`
- name: `?ResourceManagerUninstallWmiApp@@YAJPEBG0@Z`
- size: `450`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callees

- `0x18000121c`
- `0x18000135c`
- `0x180002a50`
- `0x1800062ac`
- `0x180006df0`
- `0x18000c2e8`
- `0x18000cb4c`
- `0x18000f8e4`
- `0x1800110c0`
- `0x18001f420`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180006e8b`
- `KERNEL32!CloseHandle` at `0x180006e8b`
- `DMCmnUtils!DmRevertToSelf` at `0x180006f79`
- `DMCmnUtils!DmRevertToSelf` at `0x180006f79`
- `DMCmnUtils!DmImpersonate` at `0x180006e9a`
- `DMCmnUtils!DmImpersonate` at `0x180006e9a`
- `DMCmnUtils!DmGetUserTokenFromSid` at `0x180006e3a`
- `DMCmnUtils!DmGetUserTokenFromSid` at `0x180006e3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall ResourceManagerUninstallWmiApp(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int v4; // ecx
  int UserTokenFromSid; // ebx
  int v6; // r8d
  int v7; // r9d
  int v8; // eax
  bool v9; // si
  struct JobHelper *JobHelper; // r15
  unsigned int v11; // ebx
  __int64 v12; // rax
  __int64 v13; // rdx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v18; // [rsp+34h] [rbp-74h] BYREF
  unsigned int v19; // [rsp+38h] [rbp-70h] BYREF
  const unsigned __int16 *v20; // [rsp+40h] [rbp-68h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-60h] BYREF
  _BYTE v22[32]; // [rsp+50h] [rbp-58h] BYREF

  hObject = 0;
  v19 = 0;
  UserTokenFromSid = DmGetUserTokenFromSid(a2, &hObject, &v19);
  if ( UserTokenFromSid >= 0 )
  {
    CloseHandle(hObject);
    v8 = DmImpersonate(a2);
    UserTokenFromSid = v8;
    if ( v8 >= 0 )
    {
      v9 = v8 != 1;
      JobHelper = JobHelper::GetJobHelper();
      if ( JobHelper )
      {
        BYTE1(v18) = 1;
        v11 = v19;
        v12 = std::wstring::wstring(v22, a2);
        UserTokenFromSid = JobHelper::SetImpersonation(JobHelper, v12, v11);
        if ( UserTokenFromSid >= 0 )
        {
          std::wstring::wstring(v22, a1);
          UserTokenFromSid = JobHelper::DeleteWmiApp(JobHelper, v22);
          LOBYTE(v13) = 1;
          std::wstring::_Tidy(v22, v13, 0);
          if ( (unsigned int)dword_18002B000 > 5 )
          {
            v18 = UserTokenFromSid;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              v14,
              (unsigned int)byte_180024B3D,
              v15,
              v16,
              (__int64)&v18);
          }
          JobHelper::CleanupJobHelper();
        }
        else
        {
          JobHelper::CleanupJobHelper();
        }
      }
      else
      {
        UserTokenFromSid = -2147024882;
      }
      if ( v9 )
        DmRevertToSelf();
    }
  }
  else if ( (unsigned int)dword_18002B000 > 5 )
  {
    v18 = UserTokenFromSid;
    v20 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v4,
      (unsigned int)&word_180024B7E,
      v6,
      v7,
      (__int64)&v20,
      (__int64)&v18);
  }
  return (unsigned int)UserTokenFromSid;
}

```

## disassembly

```asm
0x180006df0  mov     r11, rsp
0x180006df3  mov     [r11+18h], rbx
0x180006df7  mov     [r11+20h], rsi
0x180006dfb  push    rdi
0x180006dfc  push    r12
0x180006dfe  push    r13
0x180006e00  push    r14
0x180006e02  push    r15
0x180006e04  sub     rsp, 80h
0x180006e0b  mov     rax, cs:__security_cookie
0x180006e12  xor     rax, rsp
0x180006e15  mov     [rsp+0A8h+var_38], rax
0x180006e1a  mov     r14, rdx
0x180006e1d  mov     r12, rcx
0x180006e20  xor     edi, edi
0x180006e22  mov     [rsp+0A8h+var_78], dil
0x180006e27  mov     [r11-60h], rdi
0x180006e2b  mov     [rsp+0A8h+var_70], edi
0x180006e2f  lea     r8, [r11-70h]
0x180006e33  lea     rdx, [r11-60h]
0x180006e37  mov     rcx, r14
0x180006e3a  call    cs:__imp_?DmGetUserTokenFromSid@@YAJPEBGPEAPEAXPEAK@Z; DmGetUserTokenFromSid(ushort const *,void * *,ulong *)
0x180006e41  nop     dword ptr [rax+rax+00h]
0x180006e46  mov     ebx, eax
0x180006e48  test    eax, eax
0x180006e4a  jns     short loc_180006E86
0x180006e4c  mov     eax, cs:dword_18002B000
0x180006e52  cmp     eax, 5
0x180006e55  jbe     short loc_180006E81
0x180006e57  mov     [rsp+0A8h+var_74], ebx
0x180006e5b  mov     [rsp+0A8h+var_68], r14
0x180006e60  lea     rax, [rsp+0A8h+var_74]
0x180006e65  mov     [rsp+0A8h+var_80], rax
0x180006e6a  lea     rax, [rsp+0A8h+var_68]
0x180006e6f  mov     [rsp+0A8h+var_88], rax
0x180006e74  lea     rdx, word_180024B7E
0x180006e7b  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180006e80  nop
0x180006e81  jmp     loc_180006F85
0x180006e86  mov     rcx, [rsp+0A8h+hObject]; hObject
0x180006e8b  call    cs:__imp_CloseHandle
0x180006e92  nop     dword ptr [rax+rax+00h]
0x180006e97  mov     rcx, r14
0x180006e9a  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x180006ea1  nop     dword ptr [rax+rax+00h]
0x180006ea6  mov     ebx, eax
0x180006ea8  test    eax, eax
0x180006eaa  jns     short loc_180006EB1
0x180006eac  jmp     loc_180006F85
0x180006eb1  movzx   esi, dil
0x180006eb5  mov     r13d, 1
0x180006ebb  cmp     eax, r13d
0x180006ebe  cmovnz  esi, r13d
0x180006ec2  mov     [rsp+0A8h+var_78], sil
0x180006ec7  call    ?GetJobHelper@JobHelper@@SAPEAV1@XZ; JobHelper::GetJobHelper(void)
0x180006ecc  mov     r15, rax
0x180006ecf  test    rax, rax
0x180006ed2  jnz     short loc_180006EDE
0x180006ed4  mov     ebx, 8007000Eh
0x180006ed9  jmp     loc_180006F74
0x180006ede  mov     byte ptr [rsp+0A8h+var_74+1], r13b
0x180006ee3  mov     ebx, [rsp+0A8h+var_70]
0x180006ee7  mov     rdx, r14
0x180006eea  lea     rcx, [rsp+0A8h+var_58]
0x180006eef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180006ef4  mov     r8d, ebx
0x180006ef7  mov     rdx, rax
0x180006efa  mov     rcx, r15
0x180006efd  call    ?SetImpersonation@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; JobHelper::SetImpersonation(std::wstring,ulong)
0x180006f02  mov     ebx, eax
0x180006f04  test    eax, eax
0x180006f06  jns     short loc_180006F10
0x180006f08  call    ?CleanupJobHelper@JobHelper@@SAXXZ; JobHelper::CleanupJobHelper(void)
0x180006f0d  nop
0x180006f0e  jmp     short loc_180006F74
0x180006f10  mov     rdx, r12
0x180006f13  lea     rcx, [rsp+0A8h+var_58]
0x180006f18  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180006f1d  nop
0x180006f1e  lea     rdx, [rsp+0A8h+var_58]
0x180006f23  mov     rcx, r15
0x180006f26  call    ?DeleteWmiApp@JobHelper@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; JobHelper::DeleteWmiApp(std::wstring const &)
0x180006f2b  mov     ebx, eax
0x180006f2d  xor     r8d, r8d
0x180006f30  mov     dl, r13b
0x180006f33  lea     rcx, [rsp+0A8h+var_58]
0x180006f38  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180006f3d  mov     eax, cs:dword_18002B000
0x180006f43  cmp     eax, 5
0x180006f46  jbe     short loc_180006F63
0x180006f48  mov     [rsp+0A8h+var_74], ebx
0x180006f4c  lea     rax, [rsp+0A8h+var_74]
0x180006f51  mov     [rsp+0A8h+var_88], rax
0x180006f56  lea     rdx, byte_180024B3D
0x180006f5d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180006f62  nop
0x180006f63  call    ?CleanupJobHelper@JobHelper@@SAXXZ; JobHelper::CleanupJobHelper(void)
0x180006f68  nop
0x180006f69  jmp     short loc_180006F74
0x180006f6b  mov     ebx, dword ptr [rsp+0A8h+var_68]
0x180006f6f  mov     sil, [rsp+0A8h+var_78]
0x180006f74  test    sil, sil
0x180006f77  jz      short loc_180006F85
0x180006f79  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180006f80  nop     dword ptr [rax+rax+00h]
0x180006f85  mov     eax, ebx
0x180006f87  mov     rcx, [rsp+0A8h+var_38]
0x180006f8c  xor     rcx, rsp; StackCookie
0x180006f8f  call    __security_check_cookie
0x180006f94  lea     r11, [rsp+0A8h+var_28]
0x180006f9c  mov     rbx, [r11+40h]
0x180006fa0  mov     rsi, [r11+48h]
0x180006fa4  mov     rsp, r11
0x180006fa7  pop     r15
0x180006fa9  pop     r14
0x180006fab  pop     r13
0x180006fad  pop     r12
0x180006faf  pop     rdi
0x180006fb0  retn
```
