# SrppPolicyChangeCallback

- ea: `0x140023e00`
- end: `0x140023ee2`
- name: `SrppPolicyChangeCallback`
- size: `226`
- prototype: `CALLBACK_FUNCTION`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400387a4`

## callees

- `0x140023e00`
- `0x1400293ac`
- `0x1400295e8`

## import_xrefs

- `ntoskrnl!ZwQueryLicenseValue` at `0x140023e95`
- `ntoskrnl!ZwQueryLicenseValue` at `0x140023e95`

## string_xrefs

- `0x140023e20`: `\Registry\Machine\System\CurrentControlSet\Control\AppID\`

## pseudocode

```c
void __fastcall SrppPolicyChangeCallback(__int64 CallbackContext, PVOID Argument1, PVOID Argument2)
{
  int v3; // eax
  __int64 v4; // rcx
  int v5; // [rsp+30h] [rbp-40h] BYREF
  int v6; // [rsp+34h] [rbp-3Ch] BYREF
  struct _UNICODE_STRING v7; // [rsp+38h] [rbp-38h] BYREF
  struct _UNICODE_STRING v8; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v9[3]; // [rsp+58h] [rbp-18h] BYREF
  int v10; // [rsp+98h] [rbp+28h] BYREF

  v9[0] = 1966108;
  v9[1] = L"appid-EnableV2";
  *(_QWORD *)&v8.Length = 7602290;
  v8.Buffer = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\AppID\\";
  *(_QWORD *)&v7.Length = 4849736;
  v7.Buffer = L"dbc4c77e-cf0a-44d7-8a79-5eb45d64decd";
  v10 = 0;
  v6 = 0;
  if ( (int)AiRegReadDwordValue(CallbackContext, &v8, &v7, &v6) < 0 )
  {
    v5 = 0;
    v6 = 4;
    if ( (int)ZwQueryLicenseValue(v9, &v5, &v10, 4, &v6) >= 0 && v5 == 4 && v6 == 4 )
    {
      v3 = v10;
    }
    else
    {
      v3 = 1;
      v10 = 1;
    }
    if ( v3 )
    {
      AiRegWriteDwordValue(v4, &v8, &v7, 0);
      v3 = v10;
    }
  }
  else
  {
    v3 = 1;
  }
  dword_1400196E4 = v3;
}

```

## disassembly

```asm
0x140023e00  push    rbp
0x140023e02  mov     rbp, rsp
0x140023e05  sub     rsp, 70h
0x140023e09  lea     rax, aAppidEnablev2; "appid-EnableV2"
0x140023e10  mov     [rbp+var_18], 1E001Ch
0x140023e18  mov     [rbp+var_10], rax
0x140023e1c  lea     r9, [rbp+var_3C]
0x140023e20  lea     rax, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x140023e27  mov     [rbp+var_28], 740072h
0x140023e2f  mov     [rbp+var_20], rax
0x140023e33  lea     r8, [rbp+var_38]
0x140023e37  lea     rax, aDbc4c77eCf0a44; "dbc4c77e-cf0a-44d7-8a79-5eb45d64decd"
0x140023e3e  mov     [rbp+var_38], 4A0048h
0x140023e46  lea     rdx, [rbp+var_28]
0x140023e4a  mov     [rbp+var_30], rax
0x140023e4e  mov     [rbp+arg_18], 0
0x140023e55  mov     [rbp+var_3C], 0
0x140023e5c  call    AiRegReadDwordValue
0x140023e61  test    eax, eax
0x140023e63  js      short loc_140023E6C
0x140023e65  mov     eax, 1
0x140023e6a  jmp     short loc_140023ED5
0x140023e6c  lea     rax, [rbp+var_3C]
0x140023e70  mov     [rbp+var_40], 0
0x140023e77  mov     r9d, 4
0x140023e7d  mov     [rsp+70h+var_50], rax
0x140023e82  lea     r8, [rbp+arg_18]
0x140023e86  mov     [rbp+var_3C], 4
0x140023e8d  lea     rdx, [rbp+var_40]
0x140023e91  lea     rcx, [rbp+var_18]
0x140023e95  call    cs:__imp_ZwQueryLicenseValue
0x140023e9c  nop     dword ptr [rax+rax+00h]
0x140023ea1  test    eax, eax
0x140023ea3  js      short loc_140023EB6
0x140023ea5  cmp     [rbp+var_40], 4
0x140023ea9  jnz     short loc_140023EB6
0x140023eab  cmp     [rbp+var_3C], 4
0x140023eaf  jnz     short loc_140023EB6
0x140023eb1  mov     eax, [rbp+arg_18]
0x140023eb4  jmp     short loc_140023EBE
0x140023eb6  mov     eax, 1
0x140023ebb  mov     [rbp+arg_18], eax
0x140023ebe  test    eax, eax
0x140023ec0  jz      short loc_140023ED5
0x140023ec2  xor     r9d, r9d
0x140023ec5  lea     r8, [rbp+var_38]
0x140023ec9  lea     rdx, [rbp+var_28]
0x140023ecd  call    AiRegWriteDwordValue
0x140023ed2  mov     eax, [rbp+arg_18]
0x140023ed5  mov     cs:dword_1400196E4, eax
0x140023edb  add     rsp, 70h
0x140023edf  pop     rbp
0x140023ee0  retn
```
