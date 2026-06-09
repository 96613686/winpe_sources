# BfeEventProviderFireNetEvent

- ea: `0x14002a310`
- end: `0x14002a458`
- name: `BfeEventProviderFireNetEvent`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14002a2f0`

## callees

- `0x14002a310`
- `0x14002a460`
- `0x14002a4c0`
- `0x14002a9a0`
- `0x14002aef4`
- `0x14004efd4`
- `0x140077fa0`
- `0x140078400`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14002a3c6`
- `ntoskrnl!EtwWrite` at `0x14002a3c6`
- `ntoskrnl!EtwEventEnabled` at `0x14002a382`
- `ntoskrnl!EtwEventEnabled` at `0x14002a382`

## string_xrefs

- `0x14002a43a`: `EtwWrite`

## pseudocode

```c
__int64 __fastcall BfeEventProviderFireNetEvent(REGHANDLE *a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5)
{
  int v8; // edi
  REGHANDLE v9; // rcx
  NTSTATUS v10; // eax
  __int64 result; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-1D8h] BYREF
  _QWORD UserDataCount[52]; // [rsp+40h] [rbp-1C8h] BYREF

  memset(UserDataCount, 0, 0x19Cu);
  v8 = 0;
  v9 = *a1;
  *(_QWORD *)&EventDescriptor.Id = BFE_NET_EVENT_TYPES[2 * *(unsigned int *)(a2 + 136)];
  EventDescriptor.Keyword = a5;
  if ( EtwEventEnabled(v9, &EventDescriptor)
    && (BfeNetEventTrace(a2),
        BfeNetEventConvertToData(a2, (unsigned int *)UserDataCount),
        v8 = 1,
        v10 = EtwWrite(*a1, &EventDescriptor, 0, UserDataCount[0], (PEVENT_DATA_DESCRIPTOR)&UserDataCount[1]),
        v10 < 0) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"EtwWrite",
        v10);
    }
  }
  else
  {
    result = WfpWriteNeteventToUnifiedTrace(a2, a4);
    if ( !v8 )
      return result;
  }
  return BfeNetEventFreeMemoryForDataOut(UserDataCount);
}

```

## disassembly

```asm
0x14002a310  mov     [rsp+arg_10], rbx
0x14002a315  push    rsi
0x14002a316  push    rdi
0x14002a317  push    r14
0x14002a319  sub     rsp, 1F0h
0x14002a320  mov     rax, cs:__security_cookie
0x14002a327  xor     rax, rsp
0x14002a32a  mov     [rsp+208h+var_28], rax
0x14002a332  mov     rbx, rdx
0x14002a335  mov     r14, rcx
0x14002a338  xor     eax, eax
0x14002a33a  lea     rcx, [rsp+208h+UserDataCount]; void *
0x14002a33f  xor     edx, edx; Val
0x14002a341  mov     [rsp+208h+var_1C4], eax
0x14002a345  mov     r8d, 19Ch; Size
0x14002a34b  mov     rsi, r9
0x14002a34e  call    memset
0x14002a353  mov     eax, [rbx+88h]
0x14002a359  lea     rcx, BFE_NET_EVENT_TYPES
0x14002a360  add     rax, rax
0x14002a363  lea     rdx, [rsp+208h+EventDescriptor]; EventDescriptor
0x14002a368  xor     edi, edi
0x14002a36a  movups  xmm0, xmmword ptr [rcx+rax*8]
0x14002a36e  mov     eax, [rsp+208h+arg_20]
0x14002a375  mov     rcx, [r14]; RegHandle
0x14002a378  movups  xmmword ptr [rsp+208h+EventDescriptor.Id], xmm0
0x14002a37d  mov     [rsp+208h+EventDescriptor.Keyword], rax
0x14002a382  call    cs:__imp_EtwEventEnabled
0x14002a389  nop     dword ptr [rax+rax+00h]
0x14002a38e  test    al, al
0x14002a390  jz      short loc_14002A3D6
0x14002a392  mov     rcx, rbx
0x14002a395  call    BfeNetEventTrace
0x14002a39a  lea     rdx, [rsp+208h+UserDataCount]
0x14002a39f  mov     rcx, rbx
0x14002a3a2  call    BfeNetEventConvertToData
0x14002a3a7  mov     r9d, [rsp+208h+UserDataCount]; UserDataCount
0x14002a3ac  lea     rax, [rsp+208h+var_1C0]
0x14002a3b1  mov     rcx, [r14]; RegHandle
0x14002a3b4  lea     rdx, [rsp+208h+EventDescriptor]; EventDescriptor
0x14002a3b9  xor     r8d, r8d; ActivityId
0x14002a3bc  mov     [rsp+208h+UserData], rax; UserData
0x14002a3c1  mov     edi, 1
0x14002a3c6  call    cs:__imp_EtwWrite
0x14002a3cd  nop     dword ptr [rax+rax+00h]
0x14002a3d2  test    eax, eax
0x14002a3d4  js      short loc_14002A414
0x14002a3d6  mov     rdx, rsi
0x14002a3d9  mov     rcx, rbx
0x14002a3dc  call    WfpWriteNeteventToUnifiedTrace
0x14002a3e1  test    edi, edi
0x14002a3e3  jz      short loc_14002A3EF
0x14002a3e5  lea     rcx, [rsp+208h+UserDataCount]
0x14002a3ea  call    BfeNetEventFreeMemoryForDataOut
0x14002a3ef  mov     rcx, [rsp+208h+var_28]
0x14002a3f7  xor     rcx, rsp; StackCookie
0x14002a3fa  call    __security_check_cookie
0x14002a3ff  mov     rbx, [rsp+208h+arg_10]
0x14002a407  add     rsp, 1F0h
0x14002a40e  pop     r14
0x14002a410  pop     rdi
0x14002a411  pop     rsi
0x14002a412  retn
0x14002a414  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a41b  lea     rdx, WPP_GLOBAL_Control
0x14002a422  cmp     rcx, rdx
0x14002a425  jz      short loc_14002A3E5
0x14002a427  cmp     byte ptr [rcx+29h], 2
0x14002a42b  jb      short loc_14002A3E5
0x14002a42d  test    dword ptr [rcx+2Ch], 1000h
0x14002a434  jz      short loc_14002A3E5
0x14002a436  mov     rcx, [rcx+18h]
0x14002a43a  lea     r9, aEtwwrite; "EtwWrite"
0x14002a441  mov     edx, 0Ah
0x14002a446  mov     dword ptr [rsp+208h+UserData], eax
0x14002a44a  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14002a451  call    WPP_SF_sd
0x14002a456  jmp     short loc_14002A3E5
```
