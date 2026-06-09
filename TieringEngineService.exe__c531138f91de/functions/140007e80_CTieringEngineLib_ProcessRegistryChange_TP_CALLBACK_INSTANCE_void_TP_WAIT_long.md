# CTieringEngineLib::ProcessRegistryChange(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x140007e80`
- end: `0x140007f0f`
- name: `?ProcessRegistryChange@CTieringEngineLib@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `143`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, CTieringEngineLib *Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x140004a68`
- `0x140007e80`
- `0x14000814c`
- `0x14000860c`

## pseudocode

```c
void __fastcall CTieringEngineLib::ProcessRegistryChange(
        PTP_CALLBACK_INSTANCE Instance,
        CTieringEngineLib *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  unsigned int CurrentRegistrySettings; // eax
  unsigned int v6; // eax

  CurrentRegistrySettings = CTieringEngineLib::ReadCurrentRegistrySettings(Context);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      106,
      &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
      CurrentRegistrySettings);
  }
  v6 = CTieringEngineLib::RegisterForChangeNotification(Context);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, v6);
  }
}

```

## disassembly

```asm
0x140007e80  mov     [rsp+arg_0], rbx
0x140007e85  push    rdi
0x140007e86  sub     rsp, 20h
0x140007e8a  mov     rcx, rdx; this
0x140007e8d  mov     rbx, rdx
0x140007e90  call    ?ReadCurrentRegistrySettings@CTieringEngineLib@@AEAAJXZ; CTieringEngineLib::ReadCurrentRegistrySettings(void)
0x140007e95  mov     rcx, cs:WPP_GLOBAL_Control
0x140007e9c  lea     rdi, WPP_GLOBAL_Control
0x140007ea3  cmp     rcx, rdi
0x140007ea6  jz      short loc_140007ECC
0x140007ea8  test    byte ptr [rcx+1Ch], 1
0x140007eac  jz      short loc_140007ECC
0x140007eae  cmp     byte ptr [rcx+19h], 2
0x140007eb2  jb      short loc_140007ECC
0x140007eb4  mov     rcx, [rcx+10h]
0x140007eb8  lea     r8, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x140007ebf  mov     edx, 6Ah ; 'j'
0x140007ec4  mov     r9d, eax
0x140007ec7  call    WPP_SF_d
0x140007ecc  mov     rcx, rbx; void *
0x140007ecf  call    ?RegisterForChangeNotification@CTieringEngineLib@@CAJPEAX@Z; CTieringEngineLib::RegisterForChangeNotification(void *)
0x140007ed4  mov     rcx, cs:WPP_GLOBAL_Control
0x140007edb  cmp     rcx, rdi
0x140007ede  jz      short loc_140007F04
0x140007ee0  test    byte ptr [rcx+1Ch], 1
0x140007ee4  jz      short loc_140007F04
0x140007ee6  cmp     byte ptr [rcx+19h], 2
0x140007eea  jb      short loc_140007F04
0x140007eec  mov     rcx, [rcx+10h]
0x140007ef0  lea     r8, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x140007ef7  mov     edx, 6Bh ; 'k'
0x140007efc  mov     r9d, eax
0x140007eff  call    WPP_SF_d
0x140007f04  mov     rbx, [rsp+28h+arg_0]
0x140007f09  add     rsp, 20h
0x140007f0d  pop     rdi
0x140007f0e  retn
```
