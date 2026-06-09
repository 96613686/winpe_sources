# CMidi2LoopbackMidiBidi::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x180011010`
- end: `0x1800110e6`
- name: `?SendMidiMessage@CMidi2LoopbackMidiBidi@@UEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `214`
- prototype: `__int64 __fastcall(__int64, __int64, void *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180008f64`
- `0x180011010`
- `0x1800111f8`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CMidi2LoopbackMidiBidi::SendMidiMessage(__int64 a1, __int64 a2, void *a3, __int64 a4)
{
  __int64 result; // rax
  __int64 v5; // rdx
  MidiPingBidiDevice *v6; // rcx
  __int64 v7; // rdx
  __int64 *v8; // rdx
  __int64 v9; // rcx
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  result = 0;
  if ( !a3 )
  {
    v5 = 145;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"avcore\\midi2\\transport\\diagnosticstransport\\midi2.loopbackmidibidi.cpp",
      (const char *)0x80070057LL,
      v10);
    return 2147942487LL;
  }
  if ( (unsigned int)a4 < 4 )
  {
    v5 = 146;
    goto LABEL_3;
  }
  if ( *(_BYTE *)(a1 + 57) )
  {
    v6 = *(MidiPingBidiDevice **)(a1 + 48);
    if ( !v6 )
    {
      v7 = 150;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"avcore\\midi2\\transport\\diagnosticstransport\\midi2.loopbackmidibidi.cpp",
        (const char *)0x80004003LL,
        v10);
      return 2147500035LL;
    }
    return MidiPingBidiDevice::SendMidiMessage(v6, a3, a4, a4);
  }
  else
  {
    v8 = *(__int64 **)(a1 + 40);
    if ( *(_BYTE *)(a1 + 56) )
    {
      if ( !v8 )
      {
        v7 = 155;
        goto LABEL_9;
      }
      v9 = v8[2];
    }
    else
    {
      if ( !v8 )
      {
        v7 = 160;
        goto LABEL_9;
      }
      v9 = *v8;
    }
    if ( v9 )
      return (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 24LL))(v9, 0);
  }
  return result;
}

```

## disassembly

```asm
0x180011010  sub     rsp, 48h
0x180011014  xor     eax, eax
0x180011016  mov     r10, r8
0x180011019  test    r8, r8
0x18001101c  jnz     short loc_180011044
0x18001101e  mov     edx, 91h; void *
0x180011023  mov     rcx, [rsp+48h]; this
0x180011028  lea     r8, aAvcoreMidi2Tra_1; "avcore\\midi2\\transport\\diagnosticstr"...
0x18001102f  mov     r9d, 80070057h; char *
0x180011035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001103a  mov     eax, 80070057h
0x18001103f  jmp     loc_1800110E1
0x180011044  cmp     r9d, 4
0x180011048  jnb     short loc_180011051
0x18001104a  mov     edx, 92h
0x18001104f  jmp     short loc_180011023
0x180011051  cmp     [rcx+39h], al
0x180011054  jz      short loc_180011091
0x180011056  mov     rcx, [rcx+30h]; this
0x18001105a  test    rcx, rcx
0x18001105d  jnz     short loc_180011082
0x18001105f  mov     edx, 96h; void *
0x180011064  mov     rcx, [rsp+48h]; this
0x180011069  lea     r8, aAvcoreMidi2Tra_1; "avcore\\midi2\\transport\\diagnosticstr"...
0x180011070  mov     r9d, 80004003h; char *
0x180011076  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001107b  mov     eax, 80004003h
0x180011080  jmp     short loc_1800110E1
0x180011082  mov     r8d, r9d; unsigned int
0x180011085  mov     rdx, r10; void *
0x180011088  add     rsp, 48h
0x18001108c  jmp     ?SendMidiMessage@MidiPingBidiDevice@@QEAAJPEAXI_J@Z; MidiPingBidiDevice::SendMidiMessage(void *,uint,__int64)
0x180011091  mov     rdx, [rcx+28h]
0x180011095  cmp     [rcx+38h], al
0x180011098  jz      short loc_1800110AC
0x18001109a  test    rdx, rdx
0x18001109d  jnz     short loc_1800110A6
0x18001109f  mov     edx, 9Bh
0x1800110a4  jmp     short loc_180011064
0x1800110a6  mov     rcx, [rdx+10h]
0x1800110aa  jmp     short loc_1800110BB
0x1800110ac  test    rdx, rdx
0x1800110af  jnz     short loc_1800110B8
0x1800110b1  mov     edx, 0A0h
0x1800110b6  jmp     short loc_180011064
0x1800110b8  mov     rcx, [rdx]
0x1800110bb  test    rcx, rcx
0x1800110be  jz      short loc_1800110E1
0x1800110c0  mov     rdx, [rdx+18h]
0x1800110c4  mov     rax, [rcx]
0x1800110c7  mov     [rsp+48h+var_20], rdx
0x1800110cc  mov     rdx, [rsp+48h+arg_20]
0x1800110d1  mov     [rsp+48h+var_28], rdx
0x1800110d6  xor     edx, edx
0x1800110d8  mov     rax, [rax+18h]
0x1800110dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110e1  add     rsp, 48h
0x1800110e5  retn
```
