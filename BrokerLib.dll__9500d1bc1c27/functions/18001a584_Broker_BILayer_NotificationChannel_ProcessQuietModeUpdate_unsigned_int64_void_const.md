# Broker::BILayer::NotificationChannel::ProcessQuietModeUpdate(unsigned __int64,void const *)

- ea: `0x18001a584`
- end: `0x18001a627`
- name: `?ProcessQuietModeUpdate@NotificationChannel@BILayer@Broker@@QEAAX_KPEBX@Z`
- size: `163`
- prototype: `void __fastcall(Broker::BILayer::NotificationChannel *__hidden this, unsigned __int64, const void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001a720`

## callees

- `0x18000c274`
- `0x180011658`
- `0x18001a584`
- `0x18001a7f0`

## pseudocode

```c
void __fastcall Broker::BILayer::NotificationChannel::ProcessQuietModeUpdate(
        Broker::BILayer::NotificationChannel *this,
        unsigned __int64 a2,
        unsigned int *a3)
{
  unsigned int v5; // esi
  __int64 v6; // rcx
  __int64 v7; // rcx
  void **v8; // [rsp+20h] [rbp-38h] BYREF
  _DWORD v9[12]; // [rsp+28h] [rbp-30h] BYREF
  void *v10; // [rsp+68h] [rbp+10h] BYREF

  v10 = 0;
  if ( a2 < 0x10 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v5 = *a3;
  Broker::BILayer::NotificationChannel::UnpackUserSid((__int64)this, a3 + 3, &v10);
  try
  {
    if ( a3[2] )
    {
      if ( a3[2] == 1 )
      {
        v7 = *((_QWORD *)this + 3);
        if ( *(_QWORD *)(v7 + 2872) )
          std::_Func_class<void,unsigned long,unsigned short const *,void *>::operator()(v7 + 2816, v5, 0, v10);
      }
    }
    else
    {
      v6 = *((_QWORD *)this + 3);
      if ( *(_QWORD *)(v6 + 2616) )
        std::_Func_class<void,unsigned long,unsigned short const *,void *>::operator()(v6 + 2560, v5, 0, v10);
    }
  }
  catch ( Broker::Win32Error v8 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids, v9[6]);
    v8 = &std::exception::`vftable';
    o___std_exception_destroy_0(v9);
  }
}

```

## disassembly

```asm
0x18001a584  mov     [rsp+arg_0], rbx
0x18001a589  mov     [rsp+arg_10], rsi
0x18001a58e  push    rdi
0x18001a58f  sub     rsp, 50h
0x18001a593  mov     rbx, r8
0x18001a596  mov     rdi, rcx
0x18001a599  mov     [rsp+58h+arg_8], 0
0x18001a5a2  cmp     rdx, 10h
0x18001a5a6  jnb     short loc_18001A5AD
0x18001a5a8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001a5ad  mov     esi, [rbx]
0x18001a5af  lea     rdx, [rbx+0Ch]; void *
0x18001a5b3  lea     r8, [rsp+58h+arg_8]; void **
0x18001a5b8  call    ?UnpackUserSid@NotificationChannel@BILayer@Broker@@CAX_KPEBXAEAPEAX@Z; Broker::BILayer::NotificationChannel::UnpackUserSid(unsigned __int64,void const *,void * &)
0x18001a5bd  nop
0x18001a5be  cmp     dword ptr [rbx+8], 0
0x18001a5c2  jnz     short loc_18001A5EA
0x18001a5c4  mov     rcx, [rdi+18h]
0x18001a5c8  cmp     qword ptr [rcx+0A38h], 0
0x18001a5d0  jz      short loc_18001A615
0x18001a5d2  add     rcx, 0A00h
0x18001a5d9  mov     r9, [rsp+58h+arg_8]
0x18001a5de  xor     r8d, r8d
0x18001a5e1  mov     edx, esi
0x18001a5e3  call    ??R?$_Func_class@XKPEBGPEAX@std@@QEBAXKPEBGPEAX@Z; std::_Func_class<void,ulong,ushort const *,void *>::operator()(ulong,ushort const *,void *)
0x18001a5e8  jmp     short loc_18001A615
0x18001a5ea  cmp     dword ptr [rbx+8], 1
0x18001a5ee  jnz     short loc_18001A615
0x18001a5f0  mov     rcx, [rdi+18h]
0x18001a5f4  cmp     qword ptr [rcx+0B38h], 0
0x18001a5fc  jz      short loc_18001A615
0x18001a5fe  add     rcx, 0B00h
0x18001a605  mov     r9, [rsp+58h+arg_8]
0x18001a60a  xor     r8d, r8d
0x18001a60d  mov     edx, esi
0x18001a60f  call    ??R?$_Func_class@XKPEBGPEAX@std@@QEBAXKPEBGPEAX@Z; std::_Func_class<void,ulong,ushort const *,void *>::operator()(ulong,ushort const *,void *)
0x18001a614  nop
0x18001a615  jmp     short $+2
0x18001a617  mov     rbx, [rsp+58h+arg_0]
0x18001a61c  mov     rsi, [rsp+58h+arg_10]
0x18001a621  add     rsp, 50h
0x18001a625  pop     rdi
0x18001a626  retn
```
