# CUserModeHangReport::_OnWerMiniDumpCallback(int *,_MINIDUMP_CALLBACK_INPUT *,_MINIDUMP_CALLBACK_OUTPUT *,void (*)(void *,ulong,wchar_t const *,char *),void *)

- ea: `0x140026d80`
- end: `0x140026eca`
- name: `?_OnWerMiniDumpCallback@CUserModeHangReport@@EEAAHPEAHPEAU_MINIDUMP_CALLBACK_INPUT@@PEAU_MINIDUMP_CALLBACK_OUTPUT@@P6AXPEAXKPEB_WPEAD@Z3@Z`
- size: `330`
- prototype: `__int64 __fastcall(CUserModeHangReport *__hidden this, int *, struct _MINIDUMP_CALLBACK_INPUT *, struct _MINIDUMP_CALLBACK_OUTPUT *, void (*)(void *, unsigned int, const wchar_t *, char *), void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400166ec`
- `0x140026d80`

## import_xrefs

- `wer!WerpStitchedMinidumpVmPostReadCallback` at `0x140026e62`
- `wer!WerpStitchedMinidumpVmPostReadCallback` at `0x140026e62`
- `wer!WerpStitchedMinidumpVmPreReadCallback` at `0x140026e8f`
- `wer!WerpStitchedMinidumpVmPreReadCallback` at `0x140026e8f`
- `wer!WerpStitchedMinidumpVmQueryCallback` at `0x140026ea8`
- `wer!WerpStitchedMinidumpVmQueryCallback` at `0x140026ea8`

## pseudocode

```c
__int64 __fastcall CUserModeHangReport::_OnWerMiniDumpCallback(
        CUserModeHangReport *this,
        int *a2,
        struct _MINIDUMP_CALLBACK_INPUT *a3,
        struct _MINIDUMP_CALLBACK_OUTPUT *a4)
{
  ULONG Callback; // eax

  if ( !*((_DWORD *)this + 10547) )
  {
    *a2 = 0;
    return 0;
  }
  if ( !*((_DWORD *)this + 10546) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  if ( !*((_QWORD *)this + 4627) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  if ( !*((_QWORD *)this + 4629) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  if ( !*((_QWORD *)this + 4630) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  if ( !*((_QWORD *)this + 4631) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  *a2 = 1;
  if ( a3->CallbackType == 17 )
  {
    a4->ModuleWriteFlags = 1;
  }
  else
  {
    switch ( a3->CallbackType )
    {
      case 0x12u:
        Callback = WerpStitchedMinidumpVmQueryCallback(
                     (CUserModeHangReport *)((char *)this + 36992),
                     &a4->VmQueryResult,
                     a3->IncludeModule.BaseOfImage);
        break;
      case 0x13u:
        ++*((_DWORD *)this + 9284);
        Callback = WerpStitchedMinidumpVmPreReadCallback(
                     (CUserModeHangReport *)((char *)this + 36992),
                     &a4->VmReadBytesCompleted,
                     a3->IncludeModule.BaseOfImage,
                     a3->VmPreRead.Buffer,
                     a3->Module.SizeOfImage);
        break;
      case 0x14u:
        ++*((_DWORD *)this + 9285);
        Callback = WerpStitchedMinidumpVmPostReadCallback(
                     (CUserModeHangReport *)((char *)this + 36992),
                     &a4->VmReadBytesCompleted,
                     a3->IncludeModule.BaseOfImage,
                     a3->VmPreRead.Buffer,
                     a3->Module.SizeOfImage,
                     a3->Module.CheckSum,
                     a3->Module.TimeDateStamp);
        break;
      default:
        *a2 = 0;
        return 0;
    }
    a4->ModuleWriteFlags = Callback;
  }
  return 1;
}

```

## disassembly

```asm
0x140026d80  push    rbx
0x140026d82  push    rbp
0x140026d83  push    rsi
0x140026d84  push    rdi
0x140026d85  push    r12
0x140026d87  push    r14
0x140026d89  sub     rsp, 48h
0x140026d8d  cmp     dword ptr [rcx+0A4CCh], 0
0x140026d94  mov     rsi, r9
0x140026d97  mov     rdi, r8
0x140026d9a  mov     r14, rdx
0x140026d9d  mov     rbx, rcx
0x140026da0  jnz     short loc_140026DAF
0x140026da2  mov     dword ptr [rdx], 0
0x140026da8  xor     eax, eax
0x140026daa  jmp     loc_140026EBC
0x140026daf  cmp     dword ptr [rcx+0A4C8h], 0
0x140026db6  jnz     short loc_140026DBD
0x140026db8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140026dbd  lea     rbp, [rbx+9080h]
0x140026dc4  cmp     qword ptr [rbp+18h], 0
0x140026dc9  jnz     short loc_140026DD0
0x140026dcb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140026dd0  cmp     qword ptr [rbx+90A8h], 0
0x140026dd8  jnz     short loc_140026DDF
0x140026dda  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140026ddf  cmp     qword ptr [rbx+90B0h], 0
0x140026de7  jnz     short loc_140026DEE
0x140026de9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140026dee  cmp     qword ptr [rbx+90B8h], 0
0x140026df6  jnz     short loc_140026DFD
0x140026df8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140026dfd  mov     r12d, 1
0x140026e03  mov     [r14], r12d
0x140026e06  mov     ecx, [rdi+0Ch]
0x140026e09  sub     ecx, 11h
0x140026e0c  jz      loc_140026EB6
0x140026e12  sub     ecx, r12d
0x140026e15  jz      loc_140026E9D
0x140026e1b  sub     ecx, r12d
0x140026e1e  jz      short loc_140026E72
0x140026e20  cmp     ecx, r12d
0x140026e23  jz      short loc_140026E31
0x140026e25  mov     dword ptr [r14], 0
0x140026e2c  jmp     loc_140026DA8
0x140026e31  add     [rbx+9114h], r12d
0x140026e38  lea     rdx, [rsi+4]
0x140026e3c  mov     r8d, [rdi+28h]
0x140026e40  mov     rcx, rbp
0x140026e43  mov     r9, [rdi+18h]
0x140026e47  mov     [rsp+78h+var_48], r8d
0x140026e4c  mov     r8d, [rdi+24h]
0x140026e50  mov     [rsp+78h+var_50], r8d
0x140026e55  mov     r8d, [rdi+20h]
0x140026e59  mov     [rsp+78h+var_58], r8d
0x140026e5e  mov     r8, [rdi+10h]
0x140026e62  call    cs:__imp_?WerpStitchedMinidumpVmPostReadCallback@@YAJPEAU_WERP_STITCHED_DUMP_WRITER@@PEAK_KPEAXKKJ@Z; WerpStitchedMinidumpVmPostReadCallback(_WERP_STITCHED_DUMP_WRITER *,ulong *,unsigned __int64,void *,ulong,ulong,long)
0x140026e69  nop     dword ptr [rax+rax+00h]
0x140026e6e  mov     [rsi], eax
0x140026e70  jmp     short loc_140026EB9
0x140026e72  add     [rbx+9110h], r12d
0x140026e79  lea     rdx, [rsi+4]
0x140026e7d  mov     eax, [rdi+20h]
0x140026e80  mov     rcx, rbp
0x140026e83  mov     r9, [rdi+18h]
0x140026e87  mov     r8, [rdi+10h]
0x140026e8b  mov     [rsp+78h+var_58], eax
0x140026e8f  call    cs:__imp_?WerpStitchedMinidumpVmPreReadCallback@@YAJPEAU_WERP_STITCHED_DUMP_WRITER@@PEAK_KPEAXK@Z; WerpStitchedMinidumpVmPreReadCallback(_WERP_STITCHED_DUMP_WRITER *,ulong *,unsigned __int64,void *,ulong)
0x140026e96  nop     dword ptr [rax+rax+00h]
0x140026e9b  jmp     short loc_140026E6E
0x140026e9d  mov     r8, [rdi+10h]
0x140026ea1  lea     rdx, [rsi+4]
0x140026ea5  mov     rcx, rbp
0x140026ea8  call    cs:__imp_?WerpStitchedMinidumpVmQueryCallback@@YAJPEAU_WERP_STITCHED_DUMP_WRITER@@PEAU_MINIDUMP_MEMORY_INFO@@_K@Z; WerpStitchedMinidumpVmQueryCallback(_WERP_STITCHED_DUMP_WRITER *,_MINIDUMP_MEMORY_INFO *,unsigned __int64)
0x140026eaf  nop     dword ptr [rax+rax+00h]
0x140026eb4  jmp     short loc_140026E6E
0x140026eb6  mov     [rsi], r12d
0x140026eb9  mov     eax, r12d
0x140026ebc  add     rsp, 48h
0x140026ec0  pop     r14
0x140026ec2  pop     r12
0x140026ec4  pop     rdi
0x140026ec5  pop     rsi
0x140026ec6  pop     rbp
0x140026ec7  pop     rbx
0x140026ec8  retn
```
