# ConsoleToPipeRedirector::ReadCompleteCallback(_TP_CALLBACK_INSTANCE *,void *,void *,ulong,unsigned __int64,_TP_IO *)

- ea: `0x14001c420`
- end: `0x14001c45d`
- name: `?ReadCompleteCallback@ConsoleToPipeRedirector@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z`
- size: `61`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, unsigned __int8 *Context, PVOID Overlapped, int IoResult, ULONG_PTR NumberOfBytesTransferred)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14001bff4`
- `0x14001c420`
- `0x14001cca8`

## pseudocode

```c
void __fastcall ConsoleToPipeRedirector::ReadCompleteCallback(
        PTP_CALLBACK_INSTANCE Instance,
        unsigned __int8 *Context,
        PVOID Overlapped,
        int IoResult,
        ULONG_PTR NumberOfBytesTransferred)
{
  bool v6; // sf

  v6 = IoResult < 0;
  if ( IoResult > 0 )
    v6 = 1;
  if ( !v6 )
  {
    ConsoleToPipeRedirector::GenerateInput((ConsoleToPipeRedirector *)Context, Context + 88, NumberOfBytesTransferred);
    ConsoleToPipeRedirector::StartRead((ConsoleToPipeRedirector *)Context);
  }
}

```

## disassembly

```asm
0x14001c420  push    rbx
0x14001c422  sub     rsp, 20h
0x14001c426  mov     rbx, rdx
0x14001c429  test    r9d, r9d
0x14001c42c  jle     short loc_14001C43C
0x14001c42e  movzx   r9d, r9w
0x14001c432  or      r9d, 80070000h
0x14001c439  test    r9d, r9d
0x14001c43c  js      short loc_14001C457
0x14001c43e  mov     r8d, dword ptr [rsp+28h+NumberOfBytesTransferred]; unsigned int
0x14001c443  add     rdx, 58h ; 'X'; unsigned __int8 *
0x14001c447  mov     rcx, rbx; this
0x14001c44a  call    ?GenerateInput@ConsoleToPipeRedirector@@AEAAXPEAEK@Z; ConsoleToPipeRedirector::GenerateInput(uchar *,ulong)
0x14001c44f  mov     rcx, rbx; this
0x14001c452  call    ?StartRead@ConsoleToPipeRedirector@@AEAAXXZ; ConsoleToPipeRedirector::StartRead(void)
0x14001c457  add     rsp, 20h
0x14001c45b  pop     rbx
0x14001c45c  retn
```
