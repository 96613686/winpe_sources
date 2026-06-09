# CSendReceive::Init(void)

- ea: `0x1800b35c0`
- end: `0x1800b3697`
- name: `?Init@CSendReceive@@UEAAHXZ`
- size: `215`
- prototype: `__int64 __fastcall(CSendReceive *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800063b0`
- `0x1800b35c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b360e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b3631`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b360e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b3631`

## string_xrefs

- `0x1800b3650`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`

## pseudocode

```c
__int64 __fastcall CSendReceive::Init(CSendReceive *this)
{
  unsigned int v1; // edi
  HANDLE EventA; // rax
  HANDLE v4; // rax
  int v6; // [rsp+40h] [rbp-18h]

  v1 = 1;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_DWORD *)this + 51) = 0;
  *((_DWORD *)this + 44) = 1;
  *((_QWORD *)this + 24) = 0;
  if ( !*((_QWORD *)this + 13) )
  {
    EventA = CreateEventA(0, 0, 0, 0);
    *((_QWORD *)this + 13) = EventA;
    v1 = EventA != 0;
  }
  if ( !*((_QWORD *)this + 14) )
  {
    v4 = CreateEventA(0, 1, 0, 0);
    *((_QWORD *)this + 14) = v4;
    v1 &= -(v4 != 0);
  }
  v6 = *((_DWORD *)this + 22);
  TraceStringInline(
    1,
    5,
    L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
    1726,
    L"CSendReceive::Init",
    0,
    L"Initialized CSendReceive, this=%p m_fBlockedOnSendReceive=%d",
    this,
    v6);
  return v1;
}

```

## disassembly

```asm
0x1800b35c0  mov     [rsp+arg_0], rbx
0x1800b35c5  mov     [rsp+arg_8], rsi
0x1800b35ca  push    rdi
0x1800b35cb  sub     rsp, 50h
0x1800b35cf  xor     esi, esi
0x1800b35d1  mov     edi, 1
0x1800b35d6  mov     rbx, rcx
0x1800b35d9  mov     [rcx+30h], rsi
0x1800b35dd  mov     [rcx+38h], rsi
0x1800b35e1  mov     [rcx+40h], esi
0x1800b35e4  mov     [rcx+58h], rsi
0x1800b35e8  mov     [rcx+60h], esi
0x1800b35eb  mov     [rcx+0CCh], esi
0x1800b35f1  mov     [rcx+0B0h], edi
0x1800b35f7  mov     [rcx+0C0h], rsi
0x1800b35fe  cmp     [rcx+68h], rsi
0x1800b3602  jnz     short loc_1800B361F
0x1800b3604  xor     r9d, r9d; lpName
0x1800b3607  xor     r8d, r8d; bInitialState
0x1800b360a  xor     edx, edx; bManualReset
0x1800b360c  xor     ecx, ecx; lpEventAttributes
0x1800b360e  call    cs:__imp_CreateEventA
0x1800b3614  mov     [rbx+68h], rax
0x1800b3618  neg     rax
0x1800b361b  sbb     eax, eax
0x1800b361d  and     edi, eax
0x1800b361f  cmp     [rbx+70h], rsi
0x1800b3623  jnz     short loc_1800B3642
0x1800b3625  xor     r9d, r9d; lpName
0x1800b3628  xor     r8d, r8d; bInitialState
0x1800b362b  xor     ecx, ecx; lpEventAttributes
0x1800b362d  lea     edx, [r9+1]; bManualReset
0x1800b3631  call    cs:__imp_CreateEventA
0x1800b3637  mov     [rbx+70h], rax
0x1800b363b  neg     rax
0x1800b363e  sbb     eax, eax
0x1800b3640  and     edi, eax
0x1800b3642  mov     edx, [rbx+58h]
0x1800b3645  lea     rax, aInitializedCse; "Initialized CSendReceive, this=%p m_fBl"...
0x1800b364c  mov     [rsp+58h+var_18], edx
0x1800b3650  lea     r8, aComComplusDtcD_109; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x1800b3657  mov     [rsp+58h+var_20], rbx
0x1800b365c  mov     edx, 5
0x1800b3661  mov     [rsp+58h+var_28], rax
0x1800b3666  mov     r9d, 6BEh
0x1800b366c  lea     rax, aCsendreceiveIn; "CSendReceive::Init"
0x1800b3673  mov     [rsp+58h+var_30], rsi
0x1800b3678  mov     [rsp+58h+var_38], rax
0x1800b367d  lea     ecx, [rdx-4]
0x1800b3680  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b3685  mov     rbx, [rsp+58h+arg_0]
0x1800b368a  mov     eax, edi
0x1800b368c  mov     rsi, [rsp+58h+arg_8]
0x1800b3691  add     rsp, 50h
0x1800b3695  pop     rdi
0x1800b3696  retn
```
