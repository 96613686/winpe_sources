# ATL::CAtlExeModuleT<CRAServerModule>::ParseCommandLine(ushort const *,long *)

- ea: `0x14000d6d0`
- end: `0x14000d792`
- name: `?ParseCommandLine@?$CAtlExeModuleT@VCRAServerModule@@@ATL@@QEAA_NPEBGPEAJ@Z`
- size: `194`
- prototype: `char __fastcall(__int64, const WCHAR *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000dd80`

## callees

- `0x14000d534`
- `0x14000d6d0`
- `0x14000d8e8`
- `0x14000dbdc`
- `0x14000dc74`
- `0x14000dcb8`
- `0x140015aa0`

## pseudocode

```c
char __fastcall ATL::CAtlExeModuleT<CRAServerModule>::ParseCommandLine(__int64 a1, const WCHAR *a2, int *a3)
{
  const WCHAR *OneOf; // rax
  const WCHAR *v6; // rbx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  int updated; // eax
  int v11; // eax
  wchar_t v13[4]; // [rsp+20h] [rbp-18h] BYREF

  *a3 = 0;
  wcscpy(v13, L"-/");
  while ( 1 )
  {
    OneOf = ATL::CAtlModule::FindOneOf(a2, v13);
    v6 = OneOf;
    if ( !OneOf )
      return 1;
    if ( !(unsigned int)ATL::CAtlModule::WordCmpI(OneOf, L"UnregServer") )
    {
      v11 = ATL::CAtlModuleT<CRAServerModule>::UnregisterServer(v7);
      *a3 = v11;
      if ( v11 >= 0 )
      {
        updated = CRAServerModule::UpdateRegistryAppId(0);
LABEL_10:
        *a3 = updated;
      }
      return 0;
    }
    if ( !(unsigned int)ATL::CAtlModule::WordCmpI(v6, L"RegServer") )
    {
      v8 = CRAServerModule::UpdateRegistryAppId(1);
      *a3 = v8;
      if ( v8 >= 0 )
      {
        updated = ATL::CAtlModuleT<CRAServerModule>::RegisterServer(v9);
        goto LABEL_10;
      }
      return 0;
    }
    a2 = v6;
  }
}

```

## disassembly

```asm
0x14000d6d0  mov     [rsp+arg_0], rbx
0x14000d6d5  push    rdi
0x14000d6d6  sub     rsp, 30h
0x14000d6da  mov     rax, cs:__security_cookie
0x14000d6e1  xor     rax, rsp
0x14000d6e4  mov     [rsp+38h+var_10], rax
0x14000d6e9  mov     dword ptr [r8], 0
0x14000d6f0  mov     rdi, r8
0x14000d6f3  mov     eax, dword ptr cs:asc_14001B438; "-/"
0x14000d6f9  mov     rcx, rdx; lpsz
0x14000d6fc  mov     dword ptr [rsp+38h+var_18], eax
0x14000d700  movzx   eax, word ptr cs:asc_14001B438+4; ""
0x14000d707  mov     word ptr [rsp+38h+var_18+4], ax
0x14000d70c  lea     rdx, [rsp+38h+var_18]; LPCWSTR
0x14000d711  call    ?FindOneOf@CAtlModule@ATL@@SAPEBGPEBG0@Z; ATL::CAtlModule::FindOneOf(ushort const *,ushort const *)
0x14000d716  mov     rbx, rax
0x14000d719  test    rax, rax
0x14000d71c  jz      short loc_14000D778
0x14000d71e  lea     rdx, aUnregserver; "UnregServer"
0x14000d725  mov     rcx, rax; lpsz
0x14000d728  call    ?WordCmpI@CAtlModule@ATL@@SAHPEBG0@Z; ATL::CAtlModule::WordCmpI(ushort const *,ushort const *)
0x14000d72d  test    eax, eax
0x14000d72f  jz      short loc_14000D760
0x14000d731  lea     rdx, aRegserver; "RegServer"
0x14000d738  mov     rcx, rbx; lpsz
0x14000d73b  call    ?WordCmpI@CAtlModule@ATL@@SAHPEBG0@Z; ATL::CAtlModule::WordCmpI(ushort const *,ushort const *)
0x14000d740  test    eax, eax
0x14000d742  jz      short loc_14000D749
0x14000d744  mov     rcx, rbx
0x14000d747  jmp     short loc_14000D70C
0x14000d749  mov     ecx, 1; int
0x14000d74e  call    ?UpdateRegistryAppId@CRAServerModule@@SAJH@Z; CRAServerModule::UpdateRegistryAppId(int)
0x14000d753  mov     [rdi], eax
0x14000d755  test    eax, eax
0x14000d757  js      short loc_14000D774
0x14000d759  call    ?RegisterServer@?$CAtlModuleT@VCRAServerModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CRAServerModule>::RegisterServer(int,_GUID const *)
0x14000d75e  jmp     short loc_14000D772
0x14000d760  call    ?UnregisterServer@?$CAtlModuleT@VCRAServerModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CRAServerModule>::UnregisterServer(int,_GUID const *)
0x14000d765  mov     [rdi], eax
0x14000d767  test    eax, eax
0x14000d769  js      short loc_14000D774
0x14000d76b  xor     ecx, ecx; int
0x14000d76d  call    ?UpdateRegistryAppId@CRAServerModule@@SAJH@Z; CRAServerModule::UpdateRegistryAppId(int)
0x14000d772  mov     [rdi], eax
0x14000d774  xor     al, al
0x14000d776  jmp     short loc_14000D77A
0x14000d778  mov     al, 1
0x14000d77a  mov     rcx, [rsp+38h+var_10]
0x14000d77f  xor     rcx, rsp; StackCookie
0x14000d782  call    __security_check_cookie
0x14000d787  mov     rbx, [rsp+38h+arg_0]
0x14000d78c  add     rsp, 30h
0x14000d790  pop     rdi
0x14000d791  retn
```
