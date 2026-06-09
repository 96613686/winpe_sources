# BthOpenKeyBthPortParams

- ea: `0x1402091b8`
- end: `0x140209343`
- name: `BthOpenKeyBthPortParams`
- size: `395`
- prototype: ``
- caller_count: `14`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x14014cc40`
- `0x1401ca524`
- `0x1401d239c`
- `0x1401de284`
- `0x1401de3d0`
- `0x1401de544`
- `0x1401de80c`
- `0x1401f246c`
- `0x1401f25c8`
- `0x1401f2694`
- `0x1401f270c`
- `0x1401f27b8`
- `0x140210dd0`
- `0x140211444`

## callees

- `0x140209110`
- `0x140209168`
- `0x1402091b8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140209321`
- `ntoskrnl!ZwClose` at `0x140209321`
- `ntoskrnl!ExFreePoolWithTag` at `0x14020930c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14020930c`
- `ntoskrnl!ExAllocatePool2` at `0x14020923f`
- `ntoskrnl!ExAllocatePool2` at `0x14020923f`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140209206`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140209282`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140209206`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140209282`

## string_xrefs

- `0x1402091dd`: `\Registry\Machine\System\CurrentControlSet\Services\BTHPORT\Parameters`
- `0x140209266`: `\Registry\Machine\System\CurrentControlSet\Services\BTHPORT\Parameters`

## pseudocode

```c
__int64 __fastcall BthOpenKeyBthPortParams(__int64 a1, _QWORD *a2)
{
  int PersistedStateLocation; // eax
  void *Pool2; // rdi
  int v6; // ebx
  HANDLE v7; // rcx
  int v8; // eax
  int KeySdEnforced; // eax
  unsigned int v11; // [rsp+60h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp+30h] BYREF

  v11 = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"BluetoothBthPortParams",
                             0,
                             L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\BTHPORT\\Parameters",
                             0,
                             0,
                             0,
                             &v11);
  Pool2 = 0;
  v6 = PersistedStateLocation;
  if ( PersistedStateLocation >= 0 )
  {
    v6 = -1073741823;
LABEL_3:
    v7 = 0;
    Handle = 0;
    goto LABEL_12;
  }
  if ( PersistedStateLocation == -2147483643 )
  {
    Pool2 = (void *)ExAllocatePool2(256, v11, 1818784834);
    if ( !Pool2 )
    {
      v6 = -1073741670;
      goto LABEL_3;
    }
    v6 = RtlGetPersistedStateLocation(
           L"BluetoothBthPortParams",
           0,
           L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\BTHPORT\\Parameters",
           0,
           Pool2,
           v11,
           &v11);
  }
  v7 = 0;
  Handle = 0;
  if ( v6 >= 0 )
  {
    v6 = BthOpenKey(0, Pool2, &Handle);
    if ( v6 < 0 )
      v6 = BthCreateKeySdEnforced(0, Pool2, &Handle);
    v7 = Handle;
  }
LABEL_12:
  if ( a1 )
  {
    if ( v6 >= 0 )
    {
      if ( v7 )
      {
        v8 = BthOpenKey(v7, a1, a2);
        v7 = Handle;
        v6 = v8;
        if ( v8 < 0 )
        {
          KeySdEnforced = BthCreateKeySdEnforced(Handle, a1, a2);
          v7 = Handle;
          v6 = KeySdEnforced;
        }
      }
    }
  }
  else
  {
    *a2 = v7;
    v7 = 0;
    Handle = 0;
  }
  if ( Pool2 )
  {
    ExFreePoolWithTag(Pool2, 0x6C687442u);
    v7 = Handle;
  }
  if ( v7 )
    ZwClose(v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1402091b8  mov     r11, rsp
0x1402091bb  mov     [r11+10h], rbx
0x1402091bf  mov     [r11+20h], rsi
0x1402091c3  push    rbp
0x1402091c4  push    rdi
0x1402091c5  push    r14
0x1402091c7  mov     rbp, rsp
0x1402091ca  sub     rsp, 40h
0x1402091ce  lea     rax, [rbp+arg_0]
0x1402091d2  mov     [rbp+arg_0], 0
0x1402091d9  mov     [r11-28h], rax
0x1402091dd  lea     r8, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x1402091e4  mov     r14, rdx
0x1402091e7  mov     [rsp+40h+var_18], 0
0x1402091ef  mov     rsi, rcx
0x1402091f2  mov     qword ptr [r11-38h], 0
0x1402091fa  xor     r9d, r9d
0x1402091fd  lea     rcx, aBluetoothbthpo; "BluetoothBthPortParams"
0x140209204  xor     edx, edx
0x140209206  call    cs:__imp_RtlGetPersistedStateLocation
0x14020920d  nop     dword ptr [rax+rax+00h]
0x140209212  xor     edi, edi
0x140209214  mov     ebx, eax
0x140209216  test    eax, eax
0x140209218  js      short loc_14020922A
0x14020921a  mov     ebx, 0C0000001h
0x14020921f  xor     ecx, ecx
0x140209221  mov     [rbp+Handle], rcx
0x140209225  jmp     loc_1402092C0
0x14020922a  cmp     eax, 80000005h
0x14020922f  jnz     short loc_140209290
0x140209231  mov     edx, [rbp+arg_0]
0x140209234  mov     ecx, 100h
0x140209239  mov     r8d, 6C687442h
0x14020923f  call    cs:__imp_ExAllocatePool2
0x140209246  nop     dword ptr [rax+rax+00h]
0x14020924b  mov     rdi, rax
0x14020924e  test    rax, rax
0x140209251  jnz     short loc_14020925A
0x140209253  mov     ebx, 0C000009Ah
0x140209258  jmp     short loc_14020921F
0x14020925a  lea     rax, [rbp+arg_0]
0x14020925e  xor     r9d, r9d
0x140209261  mov     [rsp+40h+var_10], rax
0x140209266  lea     r8, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x14020926d  mov     eax, [rbp+arg_0]
0x140209270  lea     rcx, aBluetoothbthpo; "BluetoothBthPortParams"
0x140209277  mov     [rsp+40h+var_18], eax
0x14020927b  xor     edx, edx
0x14020927d  mov     [rsp+40h+var_20], rdi
0x140209282  call    cs:__imp_RtlGetPersistedStateLocation
0x140209289  nop     dword ptr [rax+rax+00h]
0x14020928e  mov     ebx, eax
0x140209290  xor     ecx, ecx
0x140209292  mov     [rbp+Handle], rcx
0x140209296  test    ebx, ebx
0x140209298  js      short loc_1402092C0
0x14020929a  lea     r8, [rbp+Handle]
0x14020929e  mov     rdx, rdi
0x1402092a1  call    BthOpenKey
0x1402092a6  mov     ebx, eax
0x1402092a8  test    eax, eax
0x1402092aa  jns     short loc_1402092BC
0x1402092ac  lea     r8, [rbp+Handle]
0x1402092b0  mov     rdx, rdi
0x1402092b3  xor     ecx, ecx
0x1402092b5  call    BthCreateKeySdEnforced
0x1402092ba  mov     ebx, eax
0x1402092bc  mov     rcx, [rbp+Handle]
0x1402092c0  test    rsi, rsi
0x1402092c3  jnz     short loc_1402092D0
0x1402092c5  mov     [r14], rcx
0x1402092c8  xor     ecx, ecx
0x1402092ca  mov     [rbp+Handle], rcx
0x1402092ce  jmp     short loc_1402092FF
0x1402092d0  test    ebx, ebx
0x1402092d2  js      short loc_1402092FF
0x1402092d4  test    rcx, rcx
0x1402092d7  jz      short loc_1402092FF
0x1402092d9  mov     r8, r14
0x1402092dc  mov     rdx, rsi
0x1402092df  call    BthOpenKey
0x1402092e4  mov     rcx, [rbp+Handle]
0x1402092e8  mov     ebx, eax
0x1402092ea  test    eax, eax
0x1402092ec  jns     short loc_1402092FF
0x1402092ee  mov     r8, r14
0x1402092f1  mov     rdx, rsi
0x1402092f4  call    BthCreateKeySdEnforced
0x1402092f9  mov     rcx, [rbp+Handle]
0x1402092fd  mov     ebx, eax
0x1402092ff  test    rdi, rdi
0x140209302  jz      short loc_14020931C
0x140209304  mov     edx, 6C687442h; Tag
0x140209309  mov     rcx, rdi; P
0x14020930c  call    cs:__imp_ExFreePoolWithTag
0x140209313  nop     dword ptr [rax+rax+00h]
0x140209318  mov     rcx, [rbp+Handle]; Handle
0x14020931c  test    rcx, rcx
0x14020931f  jz      short loc_14020932D
0x140209321  call    cs:__imp_ZwClose
0x140209328  nop     dword ptr [rax+rax+00h]
0x14020932d  mov     rsi, [rsp+40h+arg_18]
0x140209332  mov     eax, ebx
0x140209334  mov     rbx, [rsp+40h+arg_8]
0x140209339  add     rsp, 40h
0x14020933d  pop     r14
0x14020933f  pop     rdi
0x140209340  pop     rbp
0x140209341  retn
```
