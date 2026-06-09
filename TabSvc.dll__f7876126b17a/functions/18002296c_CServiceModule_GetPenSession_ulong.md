# CServiceModule::GetPenSession(ulong)

- ea: `0x18002296c`
- end: `0x180022a1c`
- name: `?GetPenSession@CServiceModule@@QEAAPEAVCPenSession@@K@Z`
- size: `176`
- prototype: `struct CPenSession *__fastcall(CServiceModule *this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180023f54`

## callees

- `0x1800134f0`
- `0x18002296c`
- `0x18002b3a8`
- `0x18002b404`

## string_xrefs

- `0x180022997`: `PENSERVICE_CServiceModule::GetPenSession`
- `0x1800229f8`: `PENSERVICE_CServiceModule::GetPenSession`

## pseudocode

```c
struct CPenSession *__fastcall CServiceModule::GetPenSession(CServiceModule *this, int a2)
{
  struct _GUID *v4; // rbx
  unsigned int PenSession; // eax
  volatile signed __int32 *v6; // rdi

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      34,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::GetPenSession",
      a2);
    v4 = WPP_GLOBAL_Control;
  }
  PenSession = CServiceModule::FindPenSession(this, a2);
  if ( PenSession == -1 )
  {
    v6 = 0;
  }
  else
  {
    v6 = *(volatile signed __int32 **)(*((_QWORD *)this + 34) + 8LL * PenSession);
    if ( v6 )
    {
      _InterlockedIncrement(v6);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( v4 != (struct _GUID *)&WPP_GLOBAL_Control && (v4[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&v4[1].Data1,
      35,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::GetPenSession");
  return (struct CPenSession *)v6;
}

```

## disassembly

```asm
0x18002296c  push    rbx
0x18002296e  push    rbp
0x18002296f  push    rsi
0x180022970  push    rdi
0x180022971  sub     rsp, 38h
0x180022975  mov     edi, edx
0x180022977  mov     rsi, rcx
0x18002297a  mov     rbx, cs:WPP_GLOBAL_Control
0x180022981  lea     rbp, WPP_GLOBAL_Control
0x180022988  cmp     rbx, rbp
0x18002298b  jz      short loc_1800229BA
0x18002298d  test    byte ptr [rbx+1Ch], 10h
0x180022991  jz      short loc_1800229BA
0x180022993  mov     rcx, [rbx+10h]
0x180022997  lea     r9, aPenserviceCser_17; "PENSERVICE_CServiceModule::GetPenSessio"...
0x18002299e  mov     edx, 22h ; '"'
0x1800229a3  mov     [rsp+58h+var_38], edi
0x1800229a7  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x1800229ae  call    WPP_SF_sd
0x1800229b3  mov     rbx, cs:WPP_GLOBAL_Control
0x1800229ba  mov     edx, edi; unsigned int
0x1800229bc  mov     rcx, rsi; this
0x1800229bf  call    ?FindPenSession@CServiceModule@@QEAAHK@Z; CServiceModule::FindPenSession(ulong)
0x1800229c4  cmp     eax, 0FFFFFFFFh
0x1800229c7  jnz     short loc_1800229CD
0x1800229c9  xor     edi, edi
0x1800229cb  jmp     short loc_1800229E9
0x1800229cd  mov     ecx, eax
0x1800229cf  mov     rax, [rsi+110h]
0x1800229d6  mov     rdi, [rax+rcx*8]
0x1800229da  test    rdi, rdi
0x1800229dd  jz      short loc_1800229E9
0x1800229df  lock inc dword ptr [rdi]
0x1800229e2  mov     rbx, cs:WPP_GLOBAL_Control
0x1800229e9  cmp     rbx, rbp
0x1800229ec  jz      short loc_180022A10
0x1800229ee  test    byte ptr [rbx+1Ch], 10h
0x1800229f2  jz      short loc_180022A10
0x1800229f4  mov     rcx, [rbx+10h]
0x1800229f8  lea     r9, aPenserviceCser_17; "PENSERVICE_CServiceModule::GetPenSessio"...
0x1800229ff  mov     edx, 23h ; '#'
0x180022a04  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180022a0b  call    WPP_SF_s
0x180022a10  mov     rax, rdi
0x180022a13  add     rsp, 38h
0x180022a17  pop     rdi
0x180022a18  pop     rsi
0x180022a19  pop     rbp
0x180022a1a  pop     rbx
0x180022a1b  retn
```
