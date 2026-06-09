# Windows::Internal::Management::Provision::ConfigurationSession::QueryCapabilityRequired(ushort const *,ushort const *,int,ushort * *)

- ea: `0x18006c4c4`
- end: `0x18006c600`
- name: `?QueryCapabilityRequired@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEBG0HPEAPEAG@Z`
- size: `316`
- prototype: `__int64 __fastcall(const unsigned __int16 *, wchar_t *SubStr, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006b72c`

## callees

- `0x180004d50`
- `0x18000a2a4`
- `0x18000a8e8`
- `0x18006c4c4`
- `0x18006db38`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetString` at `0x18006c563`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18006c599`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18006c563`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18006c599`
- `DMCmnUtils!CopyString` at `0x18006c5cd`
- `DMCmnUtils!CopyString` at `0x18006c5cd`

## string_xrefs

- `0x18006c52a`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`

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
0x18006c4c4  push    rbx
0x18006c4c6  push    rsi
0x18006c4c7  push    rdi
0x18006c4c8  sub     rsp, 670h
0x18006c4cf  mov     rax, cs:__security_cookie
0x18006c4d6  xor     rax, rsp
0x18006c4d9  mov     [rsp+688h+var_28], rax
0x18006c4e1  mov     rsi, r9
0x18006c4e4  mov     qword ptr [rsp+688h+var_668], rcx; int
0x18006c4e9  test    r8d, r8d
0x18006c4ec  lea     rax, aDevice; "Device"
0x18006c4f3  mov     rdi, rdx
0x18006c4f6  lea     r9, aUser_0; "User"
0x18006c4fd  cmovz   r9, rax
0x18006c501  lea     r8, aSoftwareMicros_20; "Software\\Microsoft\\Provisioning\\CSPs"...
0x18006c508  mov     edx, 104h; unsigned __int64
0x18006c50d  lea     rcx, [rsp+688h+var_658]; unsigned __int16 *
0x18006c512  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006c517  mov     ebx, eax
0x18006c519  test    eax, eax
0x18006c51b  jns     short loc_18006C540
0x18006c51d  mov     edx, 15Ch; void *
0x18006c522  mov     rcx, [rsp+688h]; this
0x18006c52a  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006c531  mov     r9d, ebx; char *
0x18006c534  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c539  mov     eax, ebx
0x18006c53b  jmp     loc_18006C5E5
0x18006c540  lea     r9, [rsp+688h+var_238]
0x18006c548  mov     [rsp+688h+var_668], 104h
0x18006c550  lea     r8, aCapabilitiesRe; "capabilities_required"
0x18006c557  mov     rcx, 0FFFFFFFF80000002h
0x18006c55e  lea     rdx, [rsp+688h+var_658]
0x18006c563  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x18006c569  mov     ebx, eax
0x18006c56b  test    eax, eax
0x18006c56d  jns     short loc_18006C576
0x18006c56f  mov     edx, 163h
0x18006c574  jmp     short loc_18006C522
0x18006c576  lea     r9, [rsp+688h+Str]
0x18006c57e  mov     [rsp+688h+var_668], 104h
0x18006c586  lea     r8, aPoliciesAllowe; "policies_allowed"
0x18006c58d  mov     rcx, 0FFFFFFFF80000002h
0x18006c594  lea     rdx, [rsp+688h+var_658]
0x18006c599  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x18006c59f  test    eax, eax
0x18006c5a1  js      short loc_18006C5BF
0x18006c5a3  mov     rdx, rdi; SubStr
0x18006c5a6  lea     rcx, [rsp+688h+Str]; Str
0x18006c5ae  call    ?wcsstr@@YAPEAGPEAGPEBG@Z; wcsstr(ushort *,ushort const *)
0x18006c5b3  test    rax, rax
0x18006c5b6  jnz     short loc_18006C5BF
0x18006c5b8  mov     eax, 80070005h
0x18006c5bd  jmp     short loc_18006C5E5
0x18006c5bf  mov     r8, rsi
0x18006c5c2  lea     rcx, [rsp+688h+var_238]
0x18006c5ca  or      edx, 0FFFFFFFFh
0x18006c5cd  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18006c5d3  mov     ebx, eax
0x18006c5d5  test    eax, eax
0x18006c5d7  jns     short loc_18006C5E3
0x18006c5d9  mov     edx, 16Fh
0x18006c5de  jmp     loc_18006C522
0x18006c5e3  xor     eax, eax
0x18006c5e5  mov     rcx, [rsp+688h+var_28]
0x18006c5ed  xor     rcx, rsp; StackCookie
0x18006c5f0  call    __security_check_cookie
0x18006c5f5  add     rsp, 670h
0x18006c5fc  pop     rdi
0x18006c5fd  pop     rsi
0x18006c5fe  pop     rbx
0x18006c5ff  retn
```
