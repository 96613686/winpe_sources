# EdppIsDisallowedExempt

- ea: `0x14002d390`
- end: `0x14002d428`
- name: `EdppIsDisallowedExempt`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140003ec0`

## callees

- `0x1400293ac`
- `0x14002d390`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002d3f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002d3f2`

## string_xrefs

- `0x14002d3a1`: `\REGISTRY\MACHINE\System\CurrentControlSet\Control\AppID\Configuration\EDP`

## pseudocode

```c
bool __fastcall EdppIsDisallowedExempt(__int64 a1)
{
  _QWORD *v1; // rdx
  char v2; // bl
  bool v3; // zf
  __int64 v4; // rax
  const WCHAR *v5; // rdx
  __int64 v6; // rcx
  _QWORD v8[2]; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  int v10; // [rsp+50h] [rbp+10h] BYREF

  v1 = *(_QWORD **)(a1 + 72);
  v8[1] = L"\\REGISTRY\\MACHINE\\System\\CurrentControlSet\\Control\\AppID\\Configuration\\EDP";
  DestinationString = 0;
  v8[0] = 9830548;
  v2 = 0;
  v4 = *v1 - qword_1400191C8;
  v3 = *v1 == qword_1400191C8;
  v10 = 0;
  if ( v3 )
    v4 = v1[1] - qword_1400191D0;
  v5 = L"AppxDisallowedIsExempted";
  if ( v4 )
    v5 = L"ExeDisallowedIsExempted";
  RtlInitUnicodeString(&DestinationString, v5);
  if ( (int)AiRegReadDwordValue(v6, v8, &DestinationString, &v10) >= 0 )
    return v10 == 1;
  return v2;
}

```

## disassembly

```asm
0x14002d390  mov     [rsp-8+arg_8], rbx
0x14002d395  push    rbp
0x14002d396  mov     rbp, rsp
0x14002d399  sub     rsp, 40h
0x14002d39d  mov     rdx, [rcx+48h]
0x14002d3a1  lea     rax, aRegistryMachin_2; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x14002d3a8  mov     [rbp+var_18], rax
0x14002d3ac  xorps   xmm0, xmm0
0x14002d3af  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14002d3b3  mov     [rbp+var_20], 960094h
0x14002d3bb  xor     bl, bl
0x14002d3bd  mov     rax, [rdx]
0x14002d3c0  sub     rax, cs:qword_1400191C8
0x14002d3c7  mov     [rbp+arg_0], 0
0x14002d3ce  jnz     short loc_14002D3DB
0x14002d3d0  mov     rax, [rdx+8]
0x14002d3d4  sub     rax, cs:qword_1400191D0
0x14002d3db  lea     rcx, [rbp+DestinationString]; DestinationString
0x14002d3df  lea     rdx, aAppxdisallowed; "AppxDisallowedIsExempted"
0x14002d3e6  test    rax, rax
0x14002d3e9  jz      short loc_14002D3F2
0x14002d3eb  lea     rdx, aExedisallowedi; "ExeDisallowedIsExempted"
0x14002d3f2  call    cs:__imp_RtlInitUnicodeString
0x14002d3f9  nop     dword ptr [rax+rax+00h]
0x14002d3fe  lea     r9, [rbp+arg_0]
0x14002d402  lea     r8, [rbp+DestinationString]
0x14002d406  lea     rdx, [rbp+var_20]
0x14002d40a  call    AiRegReadDwordValue
0x14002d40f  test    eax, eax
0x14002d411  js      short loc_14002D41A
0x14002d413  cmp     [rbp+arg_0], 1
0x14002d417  setz    bl
0x14002d41a  mov     al, bl
0x14002d41c  mov     rbx, [rsp+40h+arg_8]
0x14002d421  add     rsp, 40h
0x14002d425  pop     rbp
0x14002d426  retn
```
