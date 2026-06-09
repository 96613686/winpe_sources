# _BrainSettings::Load_::_1_::catch$42

- ea: `0x18004afd7`
- end: `0x18004b04a`
- name: `_BrainSettings::Load_::_1_::catch$42`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x180025a38`
- `0x180026924`
- `0x18003d5e0`
- `0x18004afd7`

## string_xrefs

- `0x18004affd`: `Unable to parse OneSettings JSON file:`
- `0x18004b01f`: `Unable to parse OneSettings JSON file: %s`

## pseudocode

```c
__int64 __fastcall BrainSettings::Load_::_1_::catch_42(wil *a1, __int64 a2)
{
  int v3; // eax
  const wchar_t *v4; // rbx
  const wchar_t *v5; // r8

  v3 = wil::ResultFromCaughtException(a1);
  v4 = *(const wchar_t **)(a2 + 88);
  v5 = v4;
  if ( *((_QWORD *)v4 + 3) > 7u )
    v5 = *(const wchar_t **)v4;
  uus::UndockedUpdateTelemetry::UusOneSettingsParseFailure("Unable to parse OneSettings JSON file:", v3, v5);
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(const wchar_t **)v4;
  wil::details::in1diag3::Log_CaughtExceptionMsg(
    *(wil::details::in1diag3 **)(a2 + 440),
    (void *)0x6A,
    (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\BrainSettings.hpp",
    "Unable to parse OneSettings JSON file: %s",
    (const char *)v4);
  return 0;
}

```

## disassembly

```asm
0x18004afd7  mov     [rsp+arg_8], rdx
0x18004afdc  push    rbx
0x18004afdd  push    rbp
0x18004afde  sub     rsp, 38h
0x18004afe2  mov     rbp, rdx
0x18004afe5  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18004afea  mov     rbx, [rbp+58h]
0x18004afee  mov     r8, rbx
0x18004aff1  cmp     qword ptr [rbx+18h], 7
0x18004aff6  jbe     short loc_18004AFFB
0x18004aff8  mov     r8, [rbx]; wchar_t *
0x18004affb  mov     edx, eax; int
0x18004affd  lea     rcx, aUnableToParseO_0; "Unable to parse OneSettings JSON file:"
0x18004b004  call    ?UusOneSettingsParseFailure@UndockedUpdateTelemetry@uus@@SAXPEBDJPEB_W@Z; uus::UndockedUpdateTelemetry::UusOneSettingsParseFailure(char const *,long,wchar_t const *)
0x18004b009  cmp     qword ptr [rbx+18h], 7
0x18004b00e  jbe     short loc_18004B013
0x18004b010  mov     rbx, [rbx]
0x18004b013  mov     rcx, [rbp+1B8h]; this
0x18004b01a  mov     [rsp+48h+var_28], rbx; char *
0x18004b01f  lea     r9, aUnableToParseO; "Unable to parse OneSettings JSON file: "...
0x18004b026  lea     r8, aCW1SSrcBrainLi_1; "C:\\__w\\1\\s\\src\\brain\\lib\\BrainSe"...
0x18004b02d  mov     edx, 6Ah ; 'j'; void *
0x18004b032  call    ?Log_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Log_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x18004b037  nop
0x18004b038  mov     rax, 0
0x18004b042  add     rsp, 38h
0x18004b046  pop     rbp
0x18004b047  pop     rbx
0x18004b048  retn
```
