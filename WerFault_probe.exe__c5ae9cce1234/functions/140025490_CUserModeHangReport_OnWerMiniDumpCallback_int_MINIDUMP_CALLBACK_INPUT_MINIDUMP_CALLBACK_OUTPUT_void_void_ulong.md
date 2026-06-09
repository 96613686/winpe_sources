# CUserModeHangReport::_OnWerMiniDumpCallback(int *,_MINIDUMP_CALLBACK_INPUT *,_MINIDUMP_CALLBACK_OUTPUT *,void (*)(void *,ulong,wchar_t const *,char *),void *)

- ea: `0x140025490`
- end: `0x1400255c3`
- name: `?_OnWerMiniDumpCallback@CUserModeHangReport@@EEAAHPEAHPEAU_MINIDUMP_CALLBACK_INPUT@@PEAU_MINIDUMP_CALLBACK_OUTPUT@@P6AXPEAXKPEB_WPEAD@Z3@Z`
- size: `307`
- prototype: `__int64 __fastcall(CUserModeHangReport *__hidden this, int *, struct _MINIDUMP_CALLBACK_INPUT *, struct _MINIDUMP_CALLBACK_OUTPUT *, void (*)(void *, unsigned int, const wchar_t *, char *), void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140015b40`
- `0x140025490`

## import_xrefs

- `wer!WerpStitchedMinidumpVmPostReadCallback` at `0x14002556e`
- `wer!WerpStitchedMinidumpVmPostReadCallback` at `0x14002556e`
- `wer!WerpStitchedMinidumpVmPreReadCallback` at `0x140025595`
- `wer!WerpStitchedMinidumpVmPreReadCallback` at `0x140025595`
- `wer!WerpStitchedMinidumpVmQueryCallback` at `0x1400255a8`
- `wer!WerpStitchedMinidumpVmQueryCallback` at `0x1400255a8`

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
0x140025490  push    rbx
0x140025492  push    rbp
0x140025493  push    rsi
0x140025494  push    rdi
0x140025495  push    r12
0x140025497  push    r14
0x140025499  sub     rsp, 48h
0x14002549d  cmp     dword ptr [rcx+0A4CCh], 0
0x1400254a4  mov     rsi, r9
0x1400254a7  mov     rdi, r8
0x1400254aa  mov     r14, rdx
0x1400254ad  mov     rbx, rcx
0x1400254b0  jnz     short loc_1400254BF
0x1400254b2  mov     dword ptr [rdx], 0
0x1400254b8  xor     eax, eax
0x1400254ba  jmp     loc_1400255B6
0x1400254bf  cmp     dword ptr [rcx+0A4C8h], 0
0x1400254c6  jnz     short loc_1400254CD
0x1400254c8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1400254cd  lea     rbp, [rbx+9080h]
0x1400254d4  cmp     qword ptr [rbp+18h], 0
0x1400254d9  jnz     short loc_1400254E0
0x1400254db  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1400254e0  cmp     qword ptr [rbx+90A8h], 0
0x1400254e8  jnz     short loc_1400254EF
0x1400254ea  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1400254ef  cmp     qword ptr [rbx+90B0h], 0
0x1400254f7  jnz     short loc_1400254FE
0x1400254f9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1400254fe  cmp     qword ptr [rbx+90B8h], 0
0x140025506  jnz     short loc_14002550D
0x140025508  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002550d  mov     r12d, 1
0x140025513  mov     [r14], r12d
0x140025516  mov     ecx, [rdi+0Ch]
0x140025519  sub     ecx, 11h
0x14002551c  jz      loc_1400255B0
0x140025522  sub     ecx, r12d
0x140025525  jz      short loc_14002559D
0x140025527  sub     ecx, r12d
0x14002552a  jz      short loc_140025578
0x14002552c  cmp     ecx, r12d
0x14002552f  jz      short loc_14002553D
0x140025531  mov     dword ptr [r14], 0
0x140025538  jmp     loc_1400254B8
0x14002553d  add     [rbx+9114h], r12d
0x140025544  lea     rdx, [rsi+4]
0x140025548  mov     r8d, [rdi+28h]
0x14002554c  mov     rcx, rbp
0x14002554f  mov     r9, [rdi+18h]
0x140025553  mov     [rsp+78h+var_48], r8d
0x140025558  mov     r8d, [rdi+24h]
0x14002555c  mov     [rsp+78h+var_50], r8d
0x140025561  mov     r8d, [rdi+20h]
0x140025565  mov     [rsp+78h+var_58], r8d
0x14002556a  mov     r8, [rdi+10h]
0x14002556e  call    cs:__imp_?WerpStitchedMinidumpVmPostReadCallback@@YAJPEAU_WERP_STITCHED_DUMP_WRITER@@PEAK_KPEAXKKJ@Z; WerpStitchedMinidumpVmPostReadCallback(_WERP_STITCHED_DUMP_WRITER *,ulong *,unsigned __int64,void *,ulong,ulong,long)
0x140025574  mov     [rsi], eax
0x140025576  jmp     short loc_1400255B3
0x140025578  add     [rbx+9110h], r12d
0x14002557f  lea     rdx, [rsi+4]
0x140025583  mov     eax, [rdi+20h]
0x140025586  mov     rcx, rbp
0x140025589  mov     r9, [rdi+18h]
0x14002558d  mov     r8, [rdi+10h]
0x140025591  mov     [rsp+78h+var_58], eax
0x140025595  call    cs:__imp_?WerpStitchedMinidumpVmPreReadCallback@@YAJPEAU_WERP_STITCHED_DUMP_WRITER@@PEAK_KPEAXK@Z; WerpStitchedMinidumpVmPreReadCallback(_WERP_STITCHED_DUMP_WRITER *,ulong *,unsigned __int64,void *,ulong)
0x14002559b  jmp     short loc_140025574
0x14002559d  mov     r8, [rdi+10h]
0x1400255a1  lea     rdx, [rsi+4]
0x1400255a5  mov     rcx, rbp
0x1400255a8  call    cs:__imp_?WerpStitchedMinidumpVmQueryCallback@@YAJPEAU_WERP_STITCHED_DUMP_WRITER@@PEAU_MINIDUMP_MEMORY_INFO@@_K@Z; WerpStitchedMinidumpVmQueryCallback(_WERP_STITCHED_DUMP_WRITER *,_MINIDUMP_MEMORY_INFO *,unsigned __int64)
0x1400255ae  jmp     short loc_140025574
0x1400255b0  mov     [rsi], r12d
0x1400255b3  mov     eax, r12d
0x1400255b6  add     rsp, 48h
0x1400255ba  pop     r14
0x1400255bc  pop     r12
0x1400255be  pop     rdi
0x1400255bf  pop     rsi
0x1400255c0  pop     rbp
0x1400255c1  pop     rbx
0x1400255c2  retn
```
