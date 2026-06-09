# SrpIsOnlySmartLockerEnabledForPolicyType

- ea: `0x140035580`
- end: `0x1400356a0`
- name: `SrpIsOnlySmartLockerEnabledForPolicyType`
- size: `288`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140034550`
- `0x1400373b0`

## callees

- `0x140001450`
- `0x1400230a8`
- `0x140033130`
- `0x140035580`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14003567a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14003567a`

## string_xrefs

- `0x1400355b3`: `\REGISTRY\MACHINE\System\CurrentControlSet\Control\AppID\Configuration\SMARTLOCKER`

## pseudocode

```c
bool __fastcall SrpIsOnlySmartLockerEnabledForPolicyType(__int64 a1, int a2)
{
  __int64 v3; // rdi
  bool v4; // si
  __int64 v5; // rdx
  __int64 v6; // rcx
  _QWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  UNICODE_STRING String2; // [rsp+30h] [rbp-18h] BYREF
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  v3 = a2;
  v4 = *(int *)(a1 + 176) >= 0 && *(_DWORD *)(*(_QWORD *)(a1 + 184) + 12LL);
  *(_QWORD *)&String2.Length = 10879140;
  String2.Buffer = L"\\REGISTRY\\MACHINE\\System\\CurrentControlSet\\Control\\AppID\\Configuration\\SMARTLOCKER";
  v8[0] = 1179664;
  v8[1] = L"DISABLED";
  v10 = 0;
  if ( (int)AiRegReadQwordValue(0, &String2, v8, &v10) >= 0 && v10 )
    return 0;
  if ( v4 || !SmartlockerSmartScreenRegistryIsEnabled() && !(unsigned int)SmartlockerEnabledAsPerPolicyConverter() )
    return 0;
  v5 = *(_QWORD *)(a1 + 48 * v3 + 40);
  if ( *(_DWORD *)(v5 + 12) != 1 || *(_BYTE *)(a1 + 24 * v3 + 260) )
    return 0;
  v6 = *(unsigned int *)(v5 + 8);
  String2.Length = *(_WORD *)(v6 + v5 + 4);
  String2.MaximumLength = *(_WORD *)(v6 + v5 + 4);
  *(_DWORD *)(&String2.MaximumLength + 1) = 0;
  String2.Buffer = (PWSTR)(v5 + *(unsigned int *)(v6 + v5));
  return RtlEqualUnicodeString(&stru_1400092A8, &String2, 0) != 0;
}

```

## disassembly

```asm
0x140035580  mov     [rsp+arg_8], rbx
0x140035585  mov     [rsp+arg_10], rsi
0x14003558a  push    rdi
0x14003558b  sub     rsp, 40h
0x14003558f  cmp     dword ptr [rcx+0B0h], 0
0x140035596  mov     rbx, rcx
0x140035599  movsxd  rdi, edx
0x14003559c  jl      short loc_1400355B0
0x14003559e  mov     rax, [rcx+0B8h]
0x1400355a5  cmp     dword ptr [rax+0Ch], 0
0x1400355a9  jz      short loc_1400355B0
0x1400355ab  mov     sil, 1
0x1400355ae  jmp     short loc_1400355B3
0x1400355b0  xor     sil, sil
0x1400355b3  lea     rax, aRegistryMachin; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x1400355ba  mov     qword ptr [rsp+48h+String2.Length], 0A600A4h
0x1400355c3  mov     [rsp+48h+String2.Buffer], rax
0x1400355c8  lea     r9, [rsp+48h+arg_0]
0x1400355cd  lea     rax, aDisabled; "DISABLED"
0x1400355d4  mov     [rsp+48h+var_28], 120010h
0x1400355dd  lea     r8, [rsp+48h+var_28]
0x1400355e2  mov     [rsp+48h+var_20], rax
0x1400355e7  lea     rdx, [rsp+48h+String2]
0x1400355ec  mov     [rsp+48h+arg_0], 0
0x1400355f5  xor     ecx, ecx
0x1400355f7  call    AiRegReadQwordValue
0x1400355fc  test    eax, eax
0x1400355fe  js      short loc_14003560C
0x140035600  cmp     [rsp+48h+arg_0], 0
0x140035606  jnz     loc_14003568D
0x14003560c  test    sil, sil
0x14003560f  jnz     short loc_14003568D
0x140035611  call    SmartlockerSmartScreenRegistryIsEnabled
0x140035616  test    eax, eax
0x140035618  jnz     short loc_140035623
0x14003561a  call    SmartlockerEnabledAsPerPolicyConverter
0x14003561f  test    eax, eax
0x140035621  jz      short loc_14003568D
0x140035623  lea     rax, [rdi+rdi*2]
0x140035627  add     rax, rax
0x14003562a  mov     rdx, [rbx+rax*8+28h]
0x14003562f  cmp     dword ptr [rdx+0Ch], 1
0x140035633  jnz     short loc_14003568D
0x140035635  lea     rax, [rdi+rdi*2]
0x140035639  cmp     byte ptr [rbx+rax*8+104h], 0
0x140035641  jnz     short loc_14003568D
0x140035643  mov     ecx, [rdx+8]
0x140035646  xor     r8d, r8d; CaseInSensitive
0x140035649  movzx   eax, word ptr [rcx+rdx+4]
0x14003564e  mov     [rsp+48h+String2.Length], ax
0x140035653  movzx   eax, word ptr [rcx+rdx+4]
0x140035658  mov     [rsp+48h+String2.MaximumLength], ax
0x14003565d  xor     eax, eax
0x14003565f  mov     dword ptr [rsp+48h+String2+4], eax
0x140035663  mov     eax, [rcx+rdx]
0x140035666  lea     rcx, stru_1400092A8; String1
0x14003566d  add     rax, rdx
0x140035670  lea     rdx, [rsp+48h+String2]; String2
0x140035675  mov     [rsp+48h+String2.Buffer], rax
0x14003567a  call    cs:__imp_RtlEqualUnicodeString
0x140035681  nop     dword ptr [rax+rax+00h]
0x140035686  test    al, al
0x140035688  setnz   al
0x14003568b  jmp     short loc_14003568F
0x14003568d  xor     al, al
0x14003568f  mov     rbx, [rsp+48h+arg_8]
0x140035694  mov     rsi, [rsp+48h+arg_10]
0x140035699  add     rsp, 40h
0x14003569d  pop     rdi
0x14003569e  retn
```
