# CUsoPolicyHelper::SetActiveHours(ulong,ulong)

- ea: `0x1800281b0`
- end: `0x1800282df`
- name: `?SetActiveHours@CUsoPolicyHelper@@SAJKK@Z`
- size: `303`
- prototype: `__int64 __fastcall(char Data, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180024f14`

## callees

- `0x180007d74`
- `0x180027a2c`
- `0x180027d4c`
- `0x1800281b0`
- `0x1800282e8`

## string_xrefs

- `0x18002821d`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x18002826d`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x1800282c6`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`

## pseudocode

```c
__int64 __fastcall CUsoPolicyHelper::SetActiveHours(unsigned int Data, unsigned int a2)
{
  int ActiveHoursPolicyValues; // eax
  char v5; // dl
  int v6; // ebx
  __int64 v7; // rdx
  int EffectiveActiveHoursMaxRange; // eax
  const unsigned __int16 *v9; // rdx
  HKEY v10; // rcx
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // r9
  unsigned int v13; // esi
  unsigned int v15; // eax
  unsigned int v16; // eax
  int v17; // eax
  const unsigned __int16 *v18; // rdx
  HKEY v19; // rcx
  const unsigned __int16 *v20; // r8
  const unsigned __int16 *v21; // r9
  unsigned int v22; // edi
  int lpValueName; // [rsp+20h] [rbp-28h]
  int lpValueNamea; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v26; // [rsp+50h] [rbp+8h] BYREF
  LONG v27; // [rsp+60h] [rbp+18h] BYREF
  LONG v28; // [rsp+68h] [rbp+20h] BYREF

  if ( Data > 0x17 || a2 > 0x17 )
  {
    v6 = -2147024809;
    v7 = 420;
  }
  else
  {
    LOBYTE(v26) = 0;
    ActiveHoursPolicyValues = GetActiveHoursPolicyValues(&v28, &v27, (bool *)&v26);
    v5 = v26;
    if ( ActiveHoursPolicyValues < 0 )
      v5 = 0;
    if ( v5 )
    {
      v6 = -2145082846;
      v7 = 425;
    }
    else
    {
      v26 = 0;
      EffectiveActiveHoursMaxRange = CUsoPolicyHelper::GetEffectiveActiveHoursMaxRange(&v26);
      v13 = EffectiveActiveHoursMaxRange;
      if ( EffectiveActiveHoursMaxRange < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AD,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
          (const char *)(unsigned int)EffectiveActiveHoursMaxRange,
          lpValueName);
        return v13;
      }
      v15 = a2 + 24;
      if ( a2 >= Data )
        v15 = a2;
      v16 = v15 - Data;
      if ( v16 < 8 || v16 > v26 )
      {
        v6 = -2145082847;
        v7 = 439;
      }
      else
      {
        v17 = SetRegDword(v10, v9, v11, v12, L"ActiveHoursStart");
        v22 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1C0,
            (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
            (const char *)(unsigned int)v17,
            lpValueNamea);
          return v22;
        }
        v6 = SetRegDword(v19, v18, v20, v21, L"ActiveHoursEnd");
        if ( v6 >= 0 )
          return 0;
        v7 = 456;
      }
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
    (const char *)(unsigned int)v6,
    lpValueName);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800281b0  mov     rax, rsp
0x1800281b3  push    rbx
0x1800281b4  push    rsi
0x1800281b5  push    rdi
0x1800281b6  sub     rsp, 30h
0x1800281ba  mov     ebx, edx
0x1800281bc  mov     edi, ecx
0x1800281be  cmp     ecx, 17h
0x1800281c1  ja      loc_1800282B7
0x1800281c7  cmp     edx, 17h
0x1800281ca  ja      loc_1800282B7
0x1800281d0  lea     r8, [rax+8]; bool *
0x1800281d4  mov     byte ptr [rax+8], 0
0x1800281d8  lea     rdx, [rax+18h]; unsigned int *
0x1800281dc  lea     rcx, [rax+20h]; unsigned int *
0x1800281e0  call    ?GetActiveHoursPolicyValues@@YAJPEAK0PEA_N@Z; GetActiveHoursPolicyValues(ulong *,ulong *,bool *)
0x1800281e5  movzx   edx, byte ptr [rsp+48h+arg_0]
0x1800281ea  xor     ecx, ecx
0x1800281ec  test    eax, eax
0x1800281ee  cmovs   edx, ecx
0x1800281f1  test    dl, dl
0x1800281f3  jz      short loc_180028204
0x1800281f5  mov     ebx, 8024A222h
0x1800281fa  mov     edx, 1A9h
0x1800281ff  jmp     loc_1800282C1
0x180028204  mov     [rsp+48h+arg_0], ecx
0x180028208  lea     rcx, [rsp+48h+arg_0]; unsigned int *
0x18002820d  call    ?GetEffectiveActiveHoursMaxRange@CUsoPolicyHelper@@SAJPEAK@Z; CUsoPolicyHelper::GetEffectiveActiveHoursMaxRange(ulong *)
0x180028212  mov     esi, eax
0x180028214  test    eax, eax
0x180028216  jns     short loc_180028238
0x180028218  mov     rcx, [rsp+48h]; this
0x18002821d  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180028224  mov     r9d, eax; char *
0x180028227  mov     edx, 1ADh; void *
0x18002822c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028231  mov     eax, esi
0x180028233  jmp     loc_1800282D7
0x180028238  cmp     ebx, edi
0x18002823a  lea     eax, [rbx+18h]
0x18002823d  cmovnb  eax, ebx
0x180028240  sub     eax, edi
0x180028242  cmp     eax, 8
0x180028245  jb      short loc_1800282AB
0x180028247  cmp     eax, [rsp+48h+arg_0]
0x18002824b  ja      short loc_1800282AB
0x18002824d  lea     rax, ValueName; "ActiveHoursStart"
0x180028254  mov     dword ptr [rsp+48h+Data], edi; Data
0x180028258  mov     [rsp+48h+lpValueName], rax; int
0x18002825d  call    ?SetRegDword@@YAJPEAUHKEY__@@PEBG111K@Z; SetRegDword(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x180028262  mov     edi, eax
0x180028264  test    eax, eax
0x180028266  jns     short loc_180028285
0x180028268  mov     rcx, [rsp+48h]; this
0x18002826d  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180028274  mov     r9d, eax; char *
0x180028277  mov     edx, 1C0h; void *
0x18002827c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028281  mov     eax, edi
0x180028283  jmp     short loc_1800282D7
0x180028285  lea     rax, aActivehoursend; "ActiveHoursEnd"
0x18002828c  mov     dword ptr [rsp+48h+Data], ebx; Data
0x180028290  mov     [rsp+48h+lpValueName], rax; lpValueName
0x180028295  call    ?SetRegDword@@YAJPEAUHKEY__@@PEBG111K@Z; SetRegDword(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x18002829a  mov     ebx, eax
0x18002829c  test    eax, eax
0x18002829e  jns     short loc_1800282A7
0x1800282a0  mov     edx, 1C8h
0x1800282a5  jmp     short loc_1800282C1
0x1800282a7  xor     eax, eax
0x1800282a9  jmp     short loc_1800282D7
0x1800282ab  mov     ebx, 8024A221h
0x1800282b0  mov     edx, 1B7h
0x1800282b5  jmp     short loc_1800282C1
0x1800282b7  mov     ebx, 80070057h
0x1800282bc  mov     edx, 1A4h; void *
0x1800282c1  mov     rcx, [rsp+48h]; this
0x1800282c6  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800282cd  mov     r9d, ebx; char *
0x1800282d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800282d5  mov     eax, ebx
0x1800282d7  add     rsp, 30h
0x1800282db  pop     rdi
0x1800282dc  pop     rsi
0x1800282dd  pop     rbx
0x1800282de  retn
```
