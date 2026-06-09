# CUsoPolicyHelper::GetEffectiveActiveHoursValues(ulong *,ulong *)

- ea: `0x180027f2c`
- end: `0x180028019`
- name: `?GetEffectiveActiveHoursValues@CUsoPolicyHelper@@SAJPEAK0@Z`
- size: `237`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180025448`
- `0x18002552c`

## callees

- `0x180007d74`
- `0x180027a2c`
- `0x180027f2c`
- `0x180028020`

## string_xrefs

- `0x180027fa8`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`

## pseudocode

```c
__int64 __fastcall CUsoPolicyHelper::GetEffectiveActiveHoursValues(unsigned int *a1, unsigned int *a2)
{
  int ActiveHoursPolicyValues; // eax
  const unsigned __int16 *v5; // rdx
  HKEY v6; // rcx
  const unsigned __int16 *v7; // r8
  const unsigned __int16 *v8; // r9
  bool v9; // di
  LSTATUS RegDword; // eax
  const unsigned __int16 *v11; // rdx
  HKEY v12; // rcx
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // r9
  unsigned int v15; // ebx
  __int64 v16; // rdx
  __int64 result; // rax
  LSTATUS v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // ecx
  int lpValue; // [rsp+20h] [rbp-38h]
  LONG v22[10]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  bool v24; // [rsp+70h] [rbp+18h] BYREF
  unsigned int v25; // [rsp+78h] [rbp+20h] BYREF

  v25 = 0;
  v22[0] = 0;
  v24 = 0;
  ActiveHoursPolicyValues = GetActiveHoursPolicyValues((LONG *)&v25, v22, &v24);
  v9 = v24;
  if ( ActiveHoursPolicyValues >= 0 && v24 )
    goto LABEL_13;
  RegDword = GetRegDword(v6, v5, v7, v8, L"ActiveHoursStart", &v25);
  v15 = RegDword;
  if ( RegDword >= 0 )
  {
    v18 = GetRegDword(v12, v11, v13, v14, L"ActiveHoursEnd", v22);
    v15 = v18;
    if ( v18 >= 0 )
    {
      v9 = 1;
    }
    else if ( v18 != -2147024894 )
    {
      v16 = 311;
      goto LABEL_6;
    }
  }
  else if ( RegDword != -2147024894 )
  {
    v16 = 300;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
      (const char *)v15,
      lpValue);
    return v15;
  }
  if ( v9 )
  {
LABEL_13:
    v19 = v25;
    v20 = v22[0];
  }
  else
  {
    v19 = 8;
    v20 = 17;
  }
  *a1 = v19;
  result = 0;
  *a2 = v20;
  return result;
}

```

## disassembly

```asm
0x180027f2c  mov     rax, rsp
0x180027f2f  mov     [rax+8], rbx
0x180027f33  push    rsi
0x180027f34  push    rdi
0x180027f35  push    r14
0x180027f37  sub     rsp, 40h
0x180027f3b  mov     rsi, rdx
0x180027f3e  mov     dword ptr [rax+20h], 0
0x180027f45  mov     r14, rcx
0x180027f48  mov     dword ptr [rax-28h], 0
0x180027f4f  lea     rdx, [rax-28h]; unsigned int *
0x180027f53  mov     byte ptr [rax+18h], 0
0x180027f57  lea     rcx, [rax+20h]; unsigned int *
0x180027f5b  lea     r8, [rax+18h]; bool *
0x180027f5f  call    ?GetActiveHoursPolicyValues@@YAJPEAK0PEA_N@Z; GetActiveHoursPolicyValues(ulong *,ulong *,bool *)
0x180027f64  mov     dil, [rsp+58h+arg_10]
0x180027f69  test    eax, eax
0x180027f6b  js      short loc_180027F76
0x180027f6d  test    dil, dil
0x180027f70  jnz     loc_180027FFC
0x180027f76  lea     rax, [rsp+58h+arg_18]
0x180027f7b  mov     [rsp+58h+var_30], rax; PVOID
0x180027f80  lea     rax, ValueName; "ActiveHoursStart"
0x180027f87  mov     [rsp+58h+lpValue], rax; int
0x180027f8c  call    ?GetRegDword@@YAJPEAUHKEY__@@PEBG111PEAK@Z; GetRegDword(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,ulong *)
0x180027f91  mov     ebx, eax
0x180027f93  test    eax, eax
0x180027f95  jns     short loc_180027FBB
0x180027f97  cmp     eax, 80070002h
0x180027f9c  jz      short loc_180027FED
0x180027f9e  mov     edx, 12Ch; void *
0x180027fa3  mov     rcx, [rsp+58h]; this
0x180027fa8  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027faf  mov     r9d, ebx; char *
0x180027fb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027fb7  mov     eax, ebx
0x180027fb9  jmp     short loc_18002800B
0x180027fbb  lea     rax, [rsp+58h+var_28]
0x180027fc0  mov     [rsp+58h+var_30], rax; PVOID
0x180027fc5  lea     rax, aActivehoursend; "ActiveHoursEnd"
0x180027fcc  mov     [rsp+58h+lpValue], rax; lpValue
0x180027fd1  call    ?GetRegDword@@YAJPEAUHKEY__@@PEBG111PEAK@Z; GetRegDword(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,ulong *)
0x180027fd6  mov     ebx, eax
0x180027fd8  test    eax, eax
0x180027fda  jns     short loc_180027FEA
0x180027fdc  cmp     eax, 80070002h
0x180027fe1  jz      short loc_180027FED
0x180027fe3  mov     edx, 137h
0x180027fe8  jmp     short loc_180027FA3
0x180027fea  mov     dil, 1
0x180027fed  test    dil, dil
0x180027ff0  jnz     short loc_180027FFC
0x180027ff2  mov     eax, 8
0x180027ff7  lea     ecx, [rax+9]
0x180027ffa  jmp     short loc_180028004
0x180027ffc  mov     eax, [rsp+58h+arg_18]
0x180028000  mov     ecx, [rsp+58h+var_28]
0x180028004  mov     [r14], eax
0x180028007  xor     eax, eax
0x180028009  mov     [rsi], ecx
0x18002800b  mov     rbx, [rsp+58h+arg_0]
0x180028010  add     rsp, 40h
0x180028014  pop     r14
0x180028016  pop     rdi
0x180028017  pop     rsi
0x180028018  retn
```
