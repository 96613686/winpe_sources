# WOSCOneSettings::SettingValueExists(ushort const *,int *)

- ea: `0x18001592c`
- end: `0x18001599b`
- name: `?SettingValueExists@WOSCOneSettings@@QEAAJPEBGPEAH@Z`
- size: `111`
- prototype: `int(WOSCOneSettings *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000e620`

## callees

- `0x18000efec`
- `0x180012e08`
- `0x18001592c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001598d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001598d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WOSCOneSettings::SettingValueExists(__int64 **this, const unsigned __int16 *a2, int *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPVOID pv; // [rsp+40h] [rbp+18h] BYREF

  if ( !a3 )
  {
    v3 = -2147467261;
    v4 = 164;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
      (const char *)v3,
      v6);
    return v3;
  }
  if ( !*this )
  {
    v3 = -2147418113;
    v4 = 165;
    goto LABEL_3;
  }
  pv = 0;
  *a3 = (int)WOSCOneSettings::GetSettingValue(this, a2, (struct CSpDynamicString *)&pv) >= 0;
  CoTaskMemFree(pv);
  return 0;
}

```

## disassembly

```asm
0x18001592c  push    rbx; int
0x18001592e  sub     rsp, 20h
0x180015932  mov     rbx, r8
0x180015935  test    r8, r8
0x180015938  jnz     short loc_18001595C
0x18001593a  mov     ebx, 80004003h
0x18001593f  mov     edx, 0A4h; void *
0x180015944  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasassessment\\woscs"...
0x18001594b  mov     r9d, ebx; char *
0x18001594e  mov     rcx, [rsp+28h]; this
0x180015953  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015958  mov     eax, ebx
0x18001595a  jmp     short loc_180015995
0x18001595c  cmp     qword ptr [rcx], 0
0x180015960  jnz     short loc_18001596E
0x180015962  mov     ebx, 8000FFFFh
0x180015967  mov     edx, 0A5h; unsigned __int16 *
0x18001596c  jmp     short loc_180015944
0x18001596e  mov     [rsp+28h+pv], 0
0x180015977  lea     r8, [rsp+28h+pv]; struct CSpDynamicString *
0x18001597c  call    ?GetSettingValue@WOSCOneSettings@@QEAAJPEBGAEAVCSpDynamicString@@@Z; WOSCOneSettings::GetSettingValue(ushort const *,CSpDynamicString &)
0x180015981  not     eax
0x180015983  shr     eax, 1Fh
0x180015986  mov     [rbx], eax
0x180015988  mov     rcx, [rsp+28h+pv]; pv
0x18001598d  call    cs:__imp_CoTaskMemFree
0x180015993  xor     eax, eax
0x180015995  add     rsp, 20h
0x180015999  pop     rbx
0x18001599a  retn
```
