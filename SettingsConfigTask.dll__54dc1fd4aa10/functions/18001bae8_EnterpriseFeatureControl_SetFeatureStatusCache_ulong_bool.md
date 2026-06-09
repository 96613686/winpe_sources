# EnterpriseFeatureControl::SetFeatureStatusCache(ulong,bool &)

- ea: `0x18001bae8`
- end: `0x18001bb7e`
- name: `?SetFeatureStatusCache@EnterpriseFeatureControl@@CAJKAEA_N@Z`
- size: `150`
- prototype: `static int(unsigned int, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018ff4`

## callees

- `0x18000970c`
- `0x18000972c`
- `0x180012940`
- `0x180017dbc`
- `0x18001bae8`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x18001bb43`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x18001bb43`

## pseudocode

```c
__int64 __fastcall EnterpriseFeatureControl::SetFeatureStatusCache(__int64 a1, bool *a2)
{
  int ProcessEnvName; // eax
  unsigned int LastError; // ebx
  const WCHAR *v5; // rdx
  const char *v6; // r9
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPCWSTR lpName; // [rsp+40h] [rbp+18h] BYREF

  lpName = 0;
  ProcessEnvName = EnterpriseFeatureControl::GetProcessEnvName(a1, (unsigned __int16 **)&lpName);
  LastError = ProcessEnvName;
  if ( ProcessEnvName >= 0 )
  {
    v5 = L"1";
    if ( !*a2 )
      v5 = L"0";
    if ( SetEnvironmentVariableW(lpName, v5) )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x31,
                    (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
                    v6);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)(unsigned int)ProcessEnvName,
      v8);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
  return LastError;
}

```

## disassembly

```asm
0x18001bae8  mov     [rsp+arg_0], rbx
0x18001baed  push    rdi; int
0x18001baee  sub     rsp, 20h
0x18001baf2  mov     rdi, rdx
0x18001baf5  mov     [rsp+28h+lpName], 0
0x18001bafe  lea     rdx, [rsp+28h+lpName]; unsigned __int16 **
0x18001bb03  call    ?GetProcessEnvName@EnterpriseFeatureControl@@CAJKPEAPEAG@Z; EnterpriseFeatureControl::GetProcessEnvName(ulong,ushort * *)
0x18001bb08  mov     ebx, eax
0x18001bb0a  test    eax, eax
0x18001bb0c  jns     short loc_18001BB29
0x18001bb0e  mov     rcx, [rsp+28h]; this
0x18001bb13  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18001bb1a  mov     r9d, eax; char *
0x18001bb1d  mov     edx, 2Fh ; '/'; void *
0x18001bb22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bb27  jmp     short loc_18001BB67
0x18001bb29  cmp     byte ptr [rdi], 0
0x18001bb2c  lea     rax, a0; "0"
0x18001bb33  mov     rcx, [rsp+28h+lpName]; lpName
0x18001bb38  lea     rdx, String2; "1"
0x18001bb3f  cmovz   rdx, rax; lpValue
0x18001bb43  call    cs:__imp_SetEnvironmentVariableW
0x18001bb49  test    eax, eax
0x18001bb4b  jnz     short loc_18001BB65
0x18001bb4d  mov     rcx, [rsp+28h]; this
0x18001bb52  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18001bb59  lea     edx, [rax+31h]; void *
0x18001bb5c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001bb61  mov     ebx, eax
0x18001bb63  jmp     short loc_18001BB67
0x18001bb65  xor     ebx, ebx
0x18001bb67  lea     rcx, [rsp+28h+lpName]
0x18001bb6c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001bb71  mov     eax, ebx
0x18001bb73  mov     rbx, [rsp+28h+arg_0]
0x18001bb78  add     rsp, 20h
0x18001bb7c  pop     rdi
0x18001bb7d  retn
```
