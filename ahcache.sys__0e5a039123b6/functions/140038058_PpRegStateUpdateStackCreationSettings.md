# PpRegStateUpdateStackCreationSettings

- ea: `0x140038058`
- end: `0x14003818e`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140036f70`

## callees

- `0x140037b70`
- `0x140038058`
- `0x140038340`
- `0x140038788`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400380e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400380e1`
- `ntoskrnl!ZwClose` at `0x14003813b`
- `ntoskrnl!ZwClose` at `0x140038174`
- `ntoskrnl!ZwClose` at `0x14003813b`
- `ntoskrnl!ZwClose` at `0x140038174`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14003814f`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14003814f`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400380c0`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400380c0`

## pseudocode

```c
__int64 __fastcall PpRegStateUpdateStackCreationSettings(int a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 *v6; // rbx
  NTSTATUS WstrKey; // ebx
  ULONG v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  HANDLE v11[3]; // [rsp+40h] [rbp-18h] BYREF
  PVOID P; // [rsp+70h] [rbp+18h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp+20h] BYREF

  P = 0;
  v11[0] = 0;
  Handle = 0;
  result = PiRegStateOpenClassKey(a1, a2, 0, 0, (__int64)&Handle);
  if ( (int)result >= 0 )
  {
    v6 = PiRegStateSysAllInherittedSecurityDescriptor;
    if ( !PiRegStateDiscriptor )
    {
      LOBYTE(v5) = 1;
      if ( (int)SeCaptureSecurityDescriptor(PiRegStateSysAllInherittedSecurityDescriptor, 0, 1, v5, &P) < 0 )
      {
        PiRegStateDiscriptor = 2;
      }
      else
      {
        PiRegStateDiscriptor = 1;
        ExFreePoolWithTag(P, 0);
      }
    }
    if ( PiRegStateDiscriptor != 1 )
      v6 = 0;
    P = v6;
    WstrKey = CmRegUtilCreateWstrKey((__int64)Handle, L"Properties", v4, v5, v6, 0, v11);
    ZwClose(Handle);
    if ( WstrKey >= 0 )
    {
      v8 = RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 8));
      WstrKey = CmRegUtilWstrValueSetFullBuffer((__int64)v11[0], v9, v10, *(_QWORD *)(a2 + 8), v8);
      ZwClose(v11[0]);
    }
    return (unsigned int)WstrKey;
  }
  return result;
}

```

## disassembly

```asm
0x140038058  mov     r11, rsp
0x14003805b  mov     [r11+8], rbx
0x14003805f  push    rdi
0x140038060  sub     rsp, 50h
0x140038064  lea     rax, [r11+20h]
0x140038068  mov     qword ptr [r11+18h], 0
0x140038070  xor     r9d, r9d
0x140038073  mov     [r11-38h], rax
0x140038077  xor     r8d, r8d
0x14003807a  mov     qword ptr [r11-18h], 0
0x140038082  mov     rdi, rdx
0x140038085  mov     qword ptr [r11+20h], 0
0x14003808d  call    PiRegStateOpenClassKey
0x140038092  test    eax, eax
0x140038094  js      loc_140038182
0x14003809a  cmp     cs:PiRegStateDiscriptor, 0
0x1400380a1  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x1400380a8  jnz     short loc_1400380F9
0x1400380aa  xor     edx, edx
0x1400380ac  lea     rax, [rsp+58h+P]
0x1400380b1  mov     r9b, 1
0x1400380b4  mov     qword ptr [rsp+58h+var_38], rax
0x1400380b9  mov     rcx, rbx
0x1400380bc  lea     r8d, [rdx+1]
0x1400380c0  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400380c7  nop     dword ptr [rax+rax+00h]
0x1400380cc  test    eax, eax
0x1400380ce  js      short loc_1400380EF
0x1400380d0  mov     rcx, [rsp+58h+P]; P
0x1400380d5  xor     edx, edx; Tag
0x1400380d7  mov     cs:PiRegStateDiscriptor, 1
0x1400380e1  call    cs:__imp_ExFreePoolWithTag
0x1400380e8  nop     dword ptr [rax+rax+00h]
0x1400380ed  jmp     short loc_1400380F9
0x1400380ef  mov     cs:PiRegStateDiscriptor, 2
0x1400380f9  mov     rcx, [rsp+58h+Handle]
0x1400380fe  lea     rdx, aProperties; "Properties"
0x140038105  xor     eax, eax
0x140038107  cmp     cs:PiRegStateDiscriptor, 1
0x14003810e  cmovnz  rbx, rax
0x140038112  lea     rax, [rsp+58h+var_18]
0x140038117  mov     [rsp+58h+var_28], rax
0x14003811c  mov     [rsp+58h+var_30], 0
0x140038125  mov     qword ptr [rsp+58h+var_38], rbx
0x14003812a  mov     [rsp+58h+P], rbx
0x14003812f  call    CmRegUtilCreateWstrKey
0x140038134  mov     rcx, [rsp+58h+Handle]; Handle
0x140038139  mov     ebx, eax
0x14003813b  call    cs:__imp_ZwClose
0x140038142  nop     dword ptr [rax+rax+00h]
0x140038147  test    ebx, ebx
0x140038149  js      short loc_140038180
0x14003814b  mov     rcx, [rdi+8]; SecurityDescriptor
0x14003814f  call    cs:__imp_RtlLengthSecurityDescriptor
0x140038156  nop     dword ptr [rax+rax+00h]
0x14003815b  mov     r9, [rdi+8]; int
0x14003815f  mov     rcx, [rsp+58h+var_18]; int
0x140038164  mov     [rsp+58h+var_38], eax; ULONG
0x140038168  call    CmRegUtilWstrValueSetFullBuffer
0x14003816d  mov     rcx, [rsp+58h+var_18]; Handle
0x140038172  mov     ebx, eax
0x140038174  call    cs:__imp_ZwClose
0x14003817b  nop     dword ptr [rax+rax+00h]
0x140038180  mov     eax, ebx
0x140038182  mov     rbx, [rsp+58h+arg_0]
0x140038187  add     rsp, 50h
0x14003818b  pop     rdi
0x14003818c  retn
```
