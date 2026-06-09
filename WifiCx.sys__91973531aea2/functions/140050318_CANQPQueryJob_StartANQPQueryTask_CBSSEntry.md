# CANQPQueryJob::StartANQPQueryTask(CBSSEntry *)

- ea: `0x140050318`
- end: `0x14005056b`
- name: `?StartANQPQueryTask@CANQPQueryJob@@AEAAHPEAVCBSSEntry@@@Z`
- size: `595`
- prototype: `__int64 __fastcall(CANQPQueryJob *__hidden this, struct CBSSEntry *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14004f2b0`
- `0x14004f700`

## callees

- `0x140009420`
- `0x14001d4c0`
- `0x14001e2c0`
- `0x14001eed0`
- `0x140022ab0`
- `0x140050318`
- `0x140061178`
- `0x140063a48`

## pseudocode

```c
__int64 __fastcall CANQPQueryJob::StartANQPQueryTask(CANQPQueryJob *this, struct CBSSEntry *a2, int a3)
{
  struct CBSSEntry *v3; // rdi
  unsigned int v5; // eax
  int v6; // edx
  int v7; // r8d
  unsigned int v8; // edi
  int v9; // r9d
  int v10; // edx
  int v11; // r8d
  DeviceCommand *v12; // rax
  signed __int32 *v13; // rsi
  DeviceCommand *v14; // rcx
  unsigned int v15; // eax
  struct DeviceCommand *v16; // rdx
  unsigned int v17; // eax
  signed __int32 v19; // [rsp+30h] [rbp-48h]
  __int64 v20; // [rsp+38h] [rbp-40h]
  int v21; // [rsp+38h] [rbp-40h]

  v3 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      a3,
      90,
      (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  *((_DWORD *)this + 1347) = *((_DWORD *)v3 + 171);
  *((_DWORD *)this + 1348) = *((_DWORD *)v3 + 170);
  if ( *((_DWORD *)this + 1382)
    || (v5 = NotificationManager::RegisterForNotifications(
               *((_QWORD *)this + 67) + 1072LL,
               103,
               0,
               *((unsigned __int16 *)this + 26)),
        (v8 = v5) == 0) )
  {
    v12 = (DeviceCommand *)operator new(0xB8u);
    v13 = (signed __int32 *)((char *)this + 16);
    if ( v12 )
      v14 = DeviceCommand::DeviceCommand(v12, *v13);
    else
      v14 = 0;
    *((_QWORD *)this + 675) = v14;
    if ( v14 )
    {
      v15 = DeviceCommand::Initialize(v14, *((_WORD *)this + 26), 108, 0x30u, (unsigned __int8 *)this + 5408);
      v8 = v15;
      if ( !v15 )
      {
        v16 = (struct DeviceCommand *)*((_QWORD *)this + 675);
        *((_DWORD *)this + 167) = 2;
        *((_BYTE *)this + 5457) = 1;
        v17 = CJobBase::QueueDeviceCommand(this, v16, v7);
        v8 = v17;
        if ( v17 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v10) = 2;
            WPP_RECORDER_SF_qDD(
              WPP_GLOBAL_Control->DeviceExtension,
              v10,
              v11,
              94,
              (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
              (char)this,
              *v13,
              v17);
          }
          *((_BYTE *)this + 5457) = 0;
        }
        goto LABEL_24;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v8;
      v9 = 93;
      v21 = v15;
    }
    else
    {
      v8 = -1073741670;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v8;
      v9 = 92;
      v21 = -1073741670;
    }
    v19 = *v13;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v8;
    v9 = 91;
    v21 = v5;
    v19 = *((_DWORD *)this + 4);
  }
  LOBYTE(v6) = 2;
  WPP_RECORDER_SF_qDD(
    WPP_GLOBAL_Control->DeviceExtension,
    v6,
    v7,
    v9,
    (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
    (char)this,
    v19,
    v21);
LABEL_24:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v10) = 5;
    LODWORD(v20) = v8;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      v11,
      95,
      (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v20);
  }
  return v8;
}

```

## disassembly

```asm
0x140050318  push    rbx
0x14005031a  push    rbp
0x14005031b  push    rsi
0x14005031c  push    rdi
0x14005031d  push    r14
0x14005031f  push    r15
0x140050321  sub     rsp, 48h
0x140050325  mov     rdi, rdx
0x140050328  mov     rbx, rcx
0x14005032b  lea     r14, WPP_RECORDER_INITIALIZED
0x140050332  xor     ebp, ebp
0x140050334  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005033b  lea     r15, WPP_42f27955ace430a2861f4465eb9690f7_Traceguids
0x140050342  jz      short loc_140050379
0x140050344  mov     rcx, cs:WPP_GLOBAL_Control
0x14005034b  cmp     byte ptr [rcx+29h], 5
0x14005034f  jnb     short loc_140050357
0x140050351  cmp     [rcx+48h], bp
0x140050355  jz      short loc_140050379
0x140050357  mov     eax, [rbx+10h]
0x14005035a  mov     r9d, 5Ah ; 'Z'
0x140050360  mov     rcx, [rcx+40h]
0x140050364  mov     dl, 5
0x140050366  mov     [rsp+78h+var_48], eax
0x14005036a  mov     [rsp+78h+var_50], rbx
0x14005036f  mov     [rsp+78h+var_58], r15
0x140050374  call    WPP_RECORDER_SF_qD
0x140050379  mov     eax, [rdi+2ACh]
0x14005037f  lea     r8, [rbx+1598h]
0x140050386  mov     [rbx+150Ch], eax
0x14005038c  mov     eax, [rdi+2A8h]
0x140050392  mov     [rbx+1510h], eax
0x140050398  cmp     [r8], ebp
0x14005039b  jnz     loc_140050422
0x1400503a1  movzx   r9d, word ptr [rbx+34h]
0x1400503a6  lea     rcx, [rbx+240h]
0x1400503ad  mov     [rsp+78h+var_50], r8
0x1400503b2  mov     rax, rbx
0x1400503b5  neg     rax
0x1400503b8  sbb     rdx, rdx
0x1400503bb  xor     r8d, r8d
0x1400503be  and     rdx, rcx
0x1400503c1  mov     rcx, [rbx+218h]
0x1400503c8  mov     [rsp+78h+var_58], rdx
0x1400503cd  add     rcx, 430h
0x1400503d4  lea     edx, [r8+67h]
0x1400503d8  call    ?RegisterForNotifications@NotificationManager@@QEAAHW4_WDI_INDICATION_TYPE@@KGPEAVINotifyDeviceIndicationCallback@@PEAK@Z; NotificationManager::RegisterForNotifications(_WDI_INDICATION_TYPE,ulong,ushort,INotifyDeviceIndicationCallback *,ulong *)
0x1400503dd  mov     edi, eax
0x1400503df  test    eax, eax
0x1400503e1  jz      short loc_140050422
0x1400503e3  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400503ea  jz      loc_14005055B
0x1400503f0  mov     ecx, [rbx+10h]
0x1400503f3  mov     r9d, 5Bh ; '['
0x1400503f9  mov     dword ptr [rsp+78h+var_40], eax
0x1400503fd  mov     [rsp+78h+var_48], ecx
0x140050401  mov     rcx, cs:WPP_GLOBAL_Control
0x140050408  mov     dl, 2
0x14005040a  mov     [rsp+78h+var_50], rbx
0x14005040f  mov     [rsp+78h+var_58], r15
0x140050414  mov     rcx, [rcx+40h]
0x140050418  call    WPP_RECORDER_SF_qDD
0x14005041d  jmp     loc_140050519
0x140050422  mov     ecx, 0B8h; unsigned __int64
0x140050427  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14005042c  lea     rsi, [rbx+10h]
0x140050430  test    rax, rax
0x140050433  jz      short loc_140050444
0x140050435  mov     edx, [rsi]; unsigned int
0x140050437  mov     rcx, rax; this
0x14005043a  call    ??0DeviceCommand@@QEAA@K@Z; DeviceCommand::DeviceCommand(ulong)
0x14005043f  mov     rcx, rax
0x140050442  jmp     short loc_140050447
0x140050444  mov     rcx, rbp; this
0x140050447  mov     [rbx+1518h], rcx
0x14005044e  test    rcx, rcx
0x140050451  jnz     short loc_140050479
0x140050453  mov     edi, 0C000009Ah
0x140050458  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005045f  jz      loc_14005055B
0x140050465  lea     r9d, [rcx+5Ch]
0x140050469  mov     dword ptr [rsp+78h+var_40], 0C000009Ah
0x140050471  mov     eax, [rsi]
0x140050473  mov     [rsp+78h+var_48], eax
0x140050477  jmp     short loc_140050401
0x140050479  movzx   edx, word ptr [rbx+34h]; unsigned __int16
0x14005047d  lea     rax, [rbx+1520h]
0x140050484  mov     r9d, 30h ; '0'; unsigned int
0x14005048a  mov     [rsp+78h+var_58], rax; unsigned __int8 *
0x14005048f  lea     r8d, [r9+3Ch]; unsigned int
0x140050493  call    ?Initialize@DeviceCommand@@QEAAHGKKPEAE@Z; DeviceCommand::Initialize(ushort,ulong,ulong,uchar *)
0x140050498  mov     edi, eax
0x14005049a  test    eax, eax
0x14005049c  jz      short loc_1400504B7
0x14005049e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400504a5  jz      loc_14005055B
0x1400504ab  mov     r9d, 5Dh ; ']'
0x1400504b1  mov     dword ptr [rsp+78h+var_40], eax
0x1400504b5  jmp     short loc_140050471
0x1400504b7  mov     rdx, [rbx+1518h]; struct DeviceCommand *
0x1400504be  mov     rcx, rbx; this
0x1400504c1  mov     dword ptr [rbx+29Ch], 2
0x1400504cb  mov     byte ptr [rbx+1551h], 1
0x1400504d2  call    ?QueueDeviceCommand@CJobBase@@IEAAHPEAVDeviceCommand@@@Z; CJobBase::QueueDeviceCommand(DeviceCommand *)
0x1400504d7  mov     edi, eax
0x1400504d9  test    eax, eax
0x1400504db  jz      short loc_140050519
0x1400504dd  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400504e4  jz      short loc_140050512
0x1400504e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400504ed  mov     r9d, 5Eh ; '^'
0x1400504f3  mov     dword ptr [rsp+78h+var_40], eax
0x1400504f7  mov     dl, 2
0x1400504f9  mov     eax, [rsi]
0x1400504fb  mov     [rsp+78h+var_48], eax
0x1400504ff  mov     rcx, [rcx+40h]
0x140050503  mov     [rsp+78h+var_50], rbx
0x140050508  mov     [rsp+78h+var_58], r15
0x14005050d  call    WPP_RECORDER_SF_qDD
0x140050512  mov     [rbx+1551h], bpl
0x140050519  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140050520  jz      short loc_14005055B
0x140050522  mov     rcx, cs:WPP_GLOBAL_Control
0x140050529  cmp     byte ptr [rcx+29h], 5
0x14005052d  jnb     short loc_140050535
0x14005052f  cmp     [rcx+48h], bp
0x140050533  jz      short loc_14005055B
0x140050535  mov     eax, [rbx+10h]
0x140050538  mov     r9d, 5Fh ; '_'
0x14005053e  mov     rcx, [rcx+40h]
0x140050542  mov     dl, 5
0x140050544  mov     dword ptr [rsp+78h+var_40], edi
0x140050548  mov     [rsp+78h+var_48], eax
0x14005054c  mov     [rsp+78h+var_50], rbx
0x140050551  mov     [rsp+78h+var_58], r15
0x140050556  call    WPP_RECORDER_SF_qDD
0x14005055b  mov     eax, edi
0x14005055d  add     rsp, 48h
0x140050561  pop     r15
0x140050563  pop     r14
0x140050565  pop     rdi
0x140050566  pop     rsi
0x140050567  pop     rbp
0x140050568  pop     rbx
0x140050569  retn
```
