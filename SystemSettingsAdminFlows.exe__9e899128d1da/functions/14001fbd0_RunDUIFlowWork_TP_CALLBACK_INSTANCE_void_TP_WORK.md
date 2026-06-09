# RunDUIFlowWork(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x14001fbd0`
- end: `0x14001fc81`
- name: `?RunDUIFlowWork@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `177`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14001083c`
- `0x14001fbd0`
- `0x140034444`
- `0x1400360f8`

## import_xrefs

- `ole32!CoUninitialize` at `0x14001fc75`
- `ole32!CoUninitialize` at `0x14001fc75`
- `ole32!CoInitializeEx` at `0x14001fbe0`
- `ole32!CoInitializeEx` at `0x14001fbe0`
- `DUI70!UnInitProcessPriv` at `0x14001fc6f`
- `DUI70!UnInitProcessPriv` at `0x14001fc6f`
- `DUI70!UnInitThread` at `0x14001fc62`
- `DUI70!UnInitThread` at `0x14001fc62`
- `DUI70!StartMessagePump` at `0x14001fc4f`
- `DUI70!StartMessagePump` at `0x14001fc4f`
- `DUI70!InitThread` at `0x14001fc14`
- `DUI70!InitThread` at `0x14001fc14`
- `DUI70!InitProcessPriv` at `0x14001fc05`
- `DUI70!InitProcessPriv` at `0x14001fc05`

## pseudocode

```c
void __fastcall RunDUIFlowWork(struct _TP_CALLBACK_INSTANCE *a1, _QWORD *a2, struct _TP_WORK *a3)
{
  __int64 v4; // r8
  const unsigned __int16 *v5; // rcx
  const struct Windows::Foundation::Rect *v6; // rdx
  CRemoveDeviceFlyout *v7; // rbx
  unsigned int v8; // edx
  CRemoveDeviceFlyout *v9; // [rsp+48h] [rbp+10h] BYREF

  if ( CoInitializeEx(0, 2u) >= 0 )
  {
    LOBYTE(v4) = 1;
    if ( (int)InitProcessPriv(14, &_ImageBase, v4) >= 0 )
    {
      if ( (int)InitThread(65538) >= 0 )
      {
        if ( !*(_DWORD *)a2 )
        {
          v5 = (const unsigned __int16 *)a2[1];
          v9 = 0;
          if ( (int)CRemoveDeviceFlyout::CreateInstance(v5, &v9) >= 0 )
          {
            v7 = v9;
            if ( (int)CRemoveDeviceFlyout::ShowFlyout(v9, v6) >= 0 )
              StartMessagePump();
            if ( v7 )
              CRemoveDeviceFlyout::`scalar deleting destructor'(v7, v8);
          }
        }
        UnInitThread();
      }
      UnInitProcessPriv(&_ImageBase);
    }
    CoUninitialize();
  }
}

```

## disassembly

```asm
0x14001fbd0  push    rbx
0x14001fbd2  sub     rsp, 30h
0x14001fbd6  mov     rbx, rdx
0x14001fbd9  xor     ecx, ecx; pvReserved
0x14001fbdb  mov     edx, 2; dwCoInit
0x14001fbe0  call    cs:__imp_CoInitializeEx
0x14001fbe6  test    eax, eax
0x14001fbe8  js      loc_14001FC7B
0x14001fbee  mov     r9b, 1
0x14001fbf1  mov     [rsp+38h+var_18], 1
0x14001fbf6  mov     r8b, r9b
0x14001fbf9  lea     rdx, __ImageBase
0x14001fc00  mov     ecx, 0Eh
0x14001fc05  call    cs:__imp_InitProcessPriv
0x14001fc0b  test    eax, eax
0x14001fc0d  js      short loc_14001FC75
0x14001fc0f  mov     ecx, 10002h
0x14001fc14  call    cs:__imp_InitThread
0x14001fc1a  test    eax, eax
0x14001fc1c  js      short loc_14001FC68
0x14001fc1e  cmp     dword ptr [rbx], 0
0x14001fc21  jnz     short loc_14001FC62
0x14001fc23  mov     rcx, [rbx+8]; unsigned __int16 *
0x14001fc27  lea     rdx, [rsp+38h+arg_8]; struct CRemoveDeviceFlyout **
0x14001fc2c  mov     [rsp+38h+arg_8], 0
0x14001fc35  call    ?CreateInstance@CRemoveDeviceFlyout@@SAJPEBGPEAPEAV1@@Z; CRemoveDeviceFlyout::CreateInstance(ushort const *,CRemoveDeviceFlyout * *)
0x14001fc3a  test    eax, eax
0x14001fc3c  js      short loc_14001FC62
0x14001fc3e  mov     rbx, [rsp+38h+arg_8]
0x14001fc43  mov     rcx, rbx; this
0x14001fc46  call    ?ShowFlyout@CRemoveDeviceFlyout@@QEAAJPEBURect@Foundation@Windows@@@Z; CRemoveDeviceFlyout::ShowFlyout(Windows::Foundation::Rect const *)
0x14001fc4b  test    eax, eax
0x14001fc4d  js      short loc_14001FC55
0x14001fc4f  call    cs:__imp_StartMessagePump
0x14001fc55  test    rbx, rbx
0x14001fc58  jz      short loc_14001FC62
0x14001fc5a  mov     rcx, rbx; this
0x14001fc5d  call    ??_GCRemoveDeviceFlyout@@QEAAPEAXI@Z; CRemoveDeviceFlyout::`scalar deleting destructor'(uint)
0x14001fc62  call    cs:__imp_UnInitThread
0x14001fc68  lea     rcx, __ImageBase
0x14001fc6f  call    cs:__imp_UnInitProcessPriv
0x14001fc75  call    cs:__imp_CoUninitialize
0x14001fc7b  add     rsp, 30h
0x14001fc7f  pop     rbx
0x14001fc80  retn
```
