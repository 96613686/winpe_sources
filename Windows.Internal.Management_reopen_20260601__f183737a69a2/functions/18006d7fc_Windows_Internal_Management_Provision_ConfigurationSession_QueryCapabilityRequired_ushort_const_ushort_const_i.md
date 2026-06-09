# Windows::Internal::Management::Provision::ConfigurationSession::QueryCapabilityRequired(ushort const *,ushort const *,int,ushort * *)

- ea: `0x18006d7fc`
- end: `0x18006d94b`
- name: `?QueryCapabilityRequired@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEBG0HPEAPEAG@Z`
- size: `335`
- prototype: `__int64 __fastcall(const unsigned __int16 *, wchar_t *SubStr, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006c9cc`

## callees

- `0x180004eb0`
- `0x18000a5c4`
- `0x18000ac30`
- `0x18006d7fc`
- `0x18006ef5c`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetString` at `0x18006d89b`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18006d8d7`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18006d89b`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18006d8d7`
- `DMCmnUtils!CopyString` at `0x18006d911`
- `DMCmnUtils!CopyString` at `0x18006d911`

## string_xrefs

- `0x18006d862`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Management::Provision::ConfigurationSession::QueryCapabilityRequired(
        const unsigned __int16 *a1,
        wchar_t *SubStr,
        int a3,
        unsigned __int16 **a4)
{
  const wchar_t *v6; // r9
  int String; // ebx
  __int64 v8; // rdx
  int v10; // [rsp+20h] [rbp-668h]
  unsigned __int16 v11[264]; // [rsp+30h] [rbp-658h] BYREF
  wchar_t Str[264]; // [rsp+240h] [rbp-448h] BYREF
  unsigned __int16 v13[264]; // [rsp+450h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+688h] [rbp+0h]

  v6 = L"User";
  if ( !a3 )
    v6 = L"Device";
  String = StringCchPrintfW(
             v11,
             0x104u,
             L"Software\\Microsoft\\Provisioning\\CSPs\\.\\%s\\Vendor\\MSFT\\PolicyManager\\%s",
             v6,
             a1);
  if ( String < 0 )
  {
    v8 = 348;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
      (const char *)(unsigned int)String,
      v10);
    return (unsigned int)String;
  }
  String = OmaDmRegistryGetString(HKEY_LOCAL_MACHINE, v11, L"capabilities_required", v13, 0x104u);
  if ( String < 0 )
  {
    v8 = 355;
    goto LABEL_5;
  }
  if ( (int)OmaDmRegistryGetString(HKEY_LOCAL_MACHINE, v11, L"policies_allowed", Str, 0x104u) >= 0
    && !wcsstr(Str, SubStr) )
  {
    return 2147942405LL;
  }
  String = CopyString(v13, 0xFFFFFFFF, a4);
  if ( String < 0 )
  {
    v8 = 367;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x18006d7fc  push    rbx
0x18006d7fe  push    rsi
0x18006d7ff  push    rdi
0x18006d800  sub     rsp, 670h
0x18006d807  mov     rax, cs:__security_cookie
0x18006d80e  xor     rax, rsp
0x18006d811  mov     [rsp+688h+var_28], rax
0x18006d819  mov     rsi, r9
0x18006d81c  mov     qword ptr [rsp+688h+var_668], rcx; int
0x18006d821  test    r8d, r8d
0x18006d824  lea     rax, aDevice; "Device"
0x18006d82b  mov     rdi, rdx
0x18006d82e  lea     r9, aUser_0; "User"
0x18006d835  cmovz   r9, rax
0x18006d839  lea     r8, aSoftwareMicros_20; "Software\\Microsoft\\Provisioning\\CSPs"...
0x18006d840  mov     edx, 104h; unsigned __int64
0x18006d845  lea     rcx, [rsp+688h+var_658]; unsigned __int16 *
0x18006d84a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006d84f  mov     ebx, eax
0x18006d851  test    eax, eax
0x18006d853  jns     short loc_18006D878
0x18006d855  mov     edx, 15Ch; void *
0x18006d85a  mov     rcx, [rsp+688h]; this
0x18006d862  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006d869  mov     r9d, ebx; char *
0x18006d86c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d871  mov     eax, ebx
0x18006d873  jmp     loc_18006D92F
0x18006d878  lea     r9, [rsp+688h+var_238]
0x18006d880  mov     [rsp+688h+var_668], 104h
0x18006d888  lea     r8, aCapabilitiesRe; "capabilities_required"
0x18006d88f  mov     rcx, 0FFFFFFFF80000002h
0x18006d896  lea     rdx, [rsp+688h+var_658]
0x18006d89b  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x18006d8a2  nop     dword ptr [rax+rax+00h]
0x18006d8a7  mov     ebx, eax
0x18006d8a9  test    eax, eax
0x18006d8ab  jns     short loc_18006D8B4
0x18006d8ad  mov     edx, 163h
0x18006d8b2  jmp     short loc_18006D85A
0x18006d8b4  lea     r9, [rsp+688h+Str]
0x18006d8bc  mov     [rsp+688h+var_668], 104h
0x18006d8c4  lea     r8, aPoliciesAllowe; "policies_allowed"
0x18006d8cb  mov     rcx, 0FFFFFFFF80000002h
0x18006d8d2  lea     rdx, [rsp+688h+var_658]
0x18006d8d7  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x18006d8de  nop     dword ptr [rax+rax+00h]
0x18006d8e3  test    eax, eax
0x18006d8e5  js      short loc_18006D903
0x18006d8e7  mov     rdx, rdi; SubStr
0x18006d8ea  lea     rcx, [rsp+688h+Str]; Str
0x18006d8f2  call    ?wcsstr@@YAPEAGPEAGPEBG@Z; wcsstr(ushort *,ushort const *)
0x18006d8f7  test    rax, rax
0x18006d8fa  jnz     short loc_18006D903
0x18006d8fc  mov     eax, 80070005h
0x18006d901  jmp     short loc_18006D92F
0x18006d903  mov     r8, rsi
0x18006d906  lea     rcx, [rsp+688h+var_238]
0x18006d90e  or      edx, 0FFFFFFFFh
0x18006d911  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18006d918  nop     dword ptr [rax+rax+00h]
0x18006d91d  mov     ebx, eax
0x18006d91f  test    eax, eax
0x18006d921  jns     short loc_18006D92D
0x18006d923  mov     edx, 16Fh
0x18006d928  jmp     loc_18006D85A
0x18006d92d  xor     eax, eax
0x18006d92f  mov     rcx, [rsp+688h+var_28]
0x18006d937  xor     rcx, rsp; StackCookie
0x18006d93a  call    __security_check_cookie
0x18006d93f  add     rsp, 670h
0x18006d946  pop     rdi
0x18006d947  pop     rsi
0x18006d948  pop     rbx
0x18006d949  retn
```
