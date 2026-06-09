# OmaDmRegistryRetrieveCurrentUsersHKCU(ulong,HKEY__ * *)

- ea: `0x180061610`
- end: `0x1800616fb`
- name: `?OmaDmRegistryRetrieveCurrentUsersHKCU@@YAJKPEAPEAUHKEY__@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(REGSAM samDesired, PHKEY phkResult)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180057c6c`
- `0x18005b914`
- `0x18005bd30`
- `0x18005d508`
- `0x1800605a8`
- `0x1800609dc`
- `0x180061610`
- `0x180069ef0`
- `0x18006cea8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800616aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800616aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OmaDmRegistryRetrieveCurrentUsersHKCU(REGSAM samDesired, PHKEY phkResult)
{
  int ActiveUserSid; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  unsigned int v7; // eax
  int v9[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  WINBOOL IsMember; // [rsp+60h] [rbp+30h] BYREF
  unsigned __int16 *v12; // [rsp+68h] [rbp+38h] BYREF

  IsMember = 0;
  v12 = 0;
  LOBYTE(v9[0]) = 0;
  BYTE2(v9[0]) = 0;
  ActiveUserSid = IsRunningInSystemContext(&IsMember);
  v5 = ActiveUserSid;
  if ( ActiveUserSid < 0 )
  {
    v6 = 1113;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\miscutils\\helpers.cpp",
      (const char *)(unsigned int)ActiveUserSid,
      v9[0]);
    goto LABEL_12;
  }
  if ( IsMember )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v12,
      0);
    ActiveUserSid = DmGetActiveUserSid(&v12);
    v5 = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      v6 = 1116;
      goto LABEL_6;
    }
    ActiveUserSid = AutoImpersonate::ImpersonateSID((AutoImpersonate *)v9, v12);
    v5 = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      v6 = 1117;
      goto LABEL_6;
    }
  }
  v7 = RegOpenCurrentUser(samDesired, phkResult);
  if ( v7 )
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x460,
           (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\miscutils\\helpers.cpp",
           (const char *)v7,
           v9[0]);
  else
    v5 = 0;
LABEL_12:
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v9);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
  return v5;
}

```

## disassembly

```asm
0x180061610  mov     [rsp-18h+arg_0], rbx
0x180061615  push    rbp
0x180061616  push    rsi
0x180061617  push    rdi
0x180061618  mov     rbp, rsp
0x18006161b  sub     rsp, 30h
0x18006161f  mov     rdi, rdx
0x180061622  mov     esi, ecx
0x180061624  mov     [rbp+IsMember], 0
0x18006162b  mov     [rbp+arg_18], 0
0x180061633  mov     [rbp+var_10], 0
0x180061637  mov     [rbp+var_E], 0
0x18006163b  lea     rcx, [rbp+IsMember]; IsMember
0x18006163f  call    IsRunningInSystemContext
0x180061644  mov     ebx, eax
0x180061646  test    eax, eax
0x180061648  jns     short loc_180061651
0x18006164a  mov     edx, 459h
0x18006164f  jmp     short loc_180061676
0x180061651  cmp     [rbp+IsMember], 0
0x180061655  jz      short loc_1800616A5
0x180061657  xor     edx, edx
0x180061659  lea     rcx, [rbp+arg_18]
0x18006165d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180061662  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x180061666  call    ?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18006166b  mov     ebx, eax
0x18006166d  test    eax, eax
0x18006166f  jns     short loc_18006168B
0x180061671  mov     edx, 45Ch; void *
0x180061676  mov     rcx, [rbp+18h]; this
0x18006167a  mov     r9d, eax; char *
0x18006167d  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\dmcmnutils\\misc"...
0x180061684  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061689  jmp     short loc_1800616D8
0x18006168b  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x18006168f  lea     rcx, [rbp+var_10]; this
0x180061693  call    ?ImpersonateSID@AutoImpersonate@@QEAAJPEBG@Z; AutoImpersonate::ImpersonateSID(ushort const *)
0x180061698  mov     ebx, eax
0x18006169a  test    eax, eax
0x18006169c  jns     short loc_1800616A5
0x18006169e  mov     edx, 45Dh
0x1800616a3  jmp     short loc_180061676
0x1800616a5  mov     rdx, rdi; phkResult
0x1800616a8  mov     ecx, esi; samDesired
0x1800616aa  call    cs:__imp_RegOpenCurrentUser
0x1800616b1  nop     dword ptr [rax+rax+00h]
0x1800616b6  test    eax, eax
0x1800616b8  jz      short loc_1800616D6
0x1800616ba  mov     rcx, [rbp+18h]; this
0x1800616be  mov     r9d, eax; char *
0x1800616c1  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\dmcmnutils\\misc"...
0x1800616c8  mov     edx, 460h; void *
0x1800616cd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800616d2  mov     ebx, eax
0x1800616d4  jmp     short loc_1800616D8
0x1800616d6  xor     ebx, ebx
0x1800616d8  lea     rcx, [rbp+var_10]; this
0x1800616dc  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x1800616e1  nop
0x1800616e2  lea     rcx, [rbp+arg_18]
0x1800616e6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800616eb  mov     eax, ebx
0x1800616ed  mov     rbx, [rsp+30h+arg_0]
0x1800616f2  add     rsp, 30h
0x1800616f6  pop     rdi
0x1800616f7  pop     rsi
0x1800616f8  pop     rbp
0x1800616f9  retn
```
