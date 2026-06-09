# GetTriageDialogType(winrt::Windows::Internal::NetworkUX::Firewall::implementation::DialogType)

- ea: `0x180012398`
- end: `0x1800123cc`
- name: `?GetTriageDialogType@@YA?AW4DialogType@FirewallUX@NetworkingTriageScenario@@W41implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001dbf0`

## callees

- `0x180010430`
- `0x180012398`

## string_xrefs

- `0x1800123bc`: `shellcommon\shell\networkux\firewallux\lib\Utils.h`

## pseudocode

```c
__int64 __fastcall GetTriageDialogType(int a1)
{
  __int64 result; // rax
  const char *v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a1 )
    return 0;
  result = 1;
  if ( a1 != 1 )
    wil::details::in1diag3::FailFast_UnexpectedMsg(
      retaddr,
      (void *)0x3B,
      (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\Utils.h",
      "Unexpected dialog type",
      v2);
  return result;
}

```

## disassembly

```asm
0x180012398  sub     rsp, 28h
0x18001239c  test    ecx, ecx
0x18001239e  jnz     short loc_1800123A7
0x1800123a0  xor     eax, eax
0x1800123a2  add     rsp, 28h
0x1800123a6  retn
0x1800123a7  mov     eax, 1
0x1800123ac  cmp     ecx, eax
0x1800123ae  jz      short loc_1800123A2
0x1800123b0  mov     rcx, [rsp+28h]; this
0x1800123b5  lea     r9, aUnexpectedDial; "Unexpected dialog type"
0x1800123bc  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\networkux\\firewall"...
0x1800123c3  lea     edx, [rax+3Ah]; void *
0x1800123c6  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
```
