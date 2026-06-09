# BthUsb_ScoRemoveChannel(_BTDEVICE *,_BTH_SCO_REMOVE_CHANNEL_ARG *)

- ea: `0x140005180`
- end: `0x14000554b`
- name: `?BthUsb_ScoRemoveChannel@@YAJPEAU_BTDEVICE@@PEAU_BTH_SCO_REMOVE_CHANNEL_ARG@@@Z`
- size: `971`
- prototype: `__int64 __fastcall(struct _BTDEVICE *, struct _BTH_SCO_REMOVE_CHANNEL_ARG *)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, installer_update`

## callees

- `0x14000175c`
- `0x1400017d4`
- `0x14000187c`
- `0x1400046b4`
- `0x140004b3c`
- `0x140004f3c`
- `0x140005180`
- `0x140005600`
- `0x1400057ac`
- `0x14000581c`
- `0x140005858`
- `0x140006f3c`
- `0x1400077c4`
- `0x140009000`
- `0x140009340`
- `0x140019ea0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000552d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000552d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140005521`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140005521`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000527e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000527e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000526d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000526d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400053e0`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400053e0`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoRemoveChannel(struct _BTDEVICE *a1, struct _BTH_SCO_REMOVE_CHANNEL_ARG *a2, int a3)
{
  unsigned __int16 *v3; // rbp
  char *v5; // rbx
  char v6; // si
  int v7; // edx
  int v8; // edi
  int v9; // r8d
  struct _DEVICE_EXTENSION *MiniportContext; // rdi
  int v11; // r8d
  int v12; // edx
  _SCO_USB_CHANNEL *v13; // r14
  int v14; // edx
  int v15; // r8d
  int v16; // edx
  int v17; // r8d
  unsigned int MaxUsedBw; // eax
  int v19; // r11d
  struct _USB_INTERFACE_DESCRIPTOR *InterfaceByFrame; // rax
  int v21; // edx
  int v22; // r8d
  char v23; // bp
  int v24; // edx
  int v25; // r8d

  v3 = (unsigned __int16 *)a2;
  v5 = 0;
  v6 = 1;
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_qH(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)a2, a3, WPP_GLOBAL_Control->DeviceExtension);
  v8 = BthUsb_ScoBasicValidation(a1, v3, 8u);
  if ( v8 >= 0 )
  {
    if ( v3[2] == 0xFFFF )
    {
      LOBYTE(v7) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v7,
        v9,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        4,
        84,
        (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
LABEL_12:
      v8 = -1073741811;
    }
    else
    {
      MiniportContext = (struct _DEVICE_EXTENSION *)a1->MiniportContext;
      v5 = (char *)a1->MiniportContext + 304;
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v5, 0);
      v11 = v3[2];
      v12 = 0;
      while ( 1 )
      {
        v13 = &MiniportContext->Sco.Channel[(unsigned __int16)v12];
        if ( v13->ConnectionHandle == (_WORD)v11 )
          break;
        LOWORD(v12) = v12 + 1;
        if ( (unsigned __int16)v12 >= 3u )
          goto LABEL_18;
      }
      if ( !v13 )
      {
LABEL_18:
        LOBYTE(v12) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v12,
          v11,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          4,
          85,
          (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
        goto LABEL_12;
      }
      BthUsb_ScoStopUsbTraffic(MiniportContext);
      v13->ConnectionHandle = -1;
      --MiniportContext->Sco.NumChannels;
      BthUsb_ScoUpdateChannelsInfo(MiniportContext);
      BthUsb_ScoUpdateWriteResources(MiniportContext);
      if ( MiniportContext->Sco.NumChannels )
      {
        MaxUsedBw = BthUsb_ScoGetMaxUsedBw(MiniportContext);
        InterfaceByFrame = BthUsb_ScoFindInterfaceByFrame(MiniportContext, v19 * (MaxUsedBw / 0x3E8) + 1, 0);
        v23 = (char)InterfaceByFrame;
        if ( InterfaceByFrame )
        {
          if ( (int)BthUsb_ScoSelectInterface(MiniportContext, InterfaceByFrame) < 0 )
          {
            LOBYTE(v24) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
            WPP_RECORDER_AND_TRACE_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              v24,
              v25,
              WPP_GLOBAL_Control->DeviceExtension,
              2,
              4,
              88,
              (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
              v23);
          }
          else
          {
            BthUsb_ScoStartUsbTraffic(MiniportContext);
          }
        }
        else
        {
          LOBYTE(v21) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v21,
            v22,
            WPP_GLOBAL_Control->DeviceExtension,
            2,
            4,
            89,
            (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
        }
      }
      else
      {
        LOBYTE(v14) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v14,
          v15,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          4,
          86,
          (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
        if ( (int)BthUsb_ScoSelectInterface(MiniportContext, 0) < 0 )
        {
          LOBYTE(v16) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v16,
            v17,
            WPP_GLOBAL_Control->DeviceExtension,
            2,
            4,
            87,
            (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
        }
        BthUsb_ScoFreeReadResources(MiniportContext);
        BthUsb_ScoFreeWriteResources(MiniportContext);
        BthUsb_ScoReleaseUsbBusInterface(MiniportContext);
        IoReleaseRemoveLockEx(&MiniportContext->RemoveLock, BthUsb_ScoAddChannel, 0x20u);
      }
      v8 = 0;
    }
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v6 = 0;
  LOBYTE(v7) = v6;
  WPP_RECORDER_AND_TRACE_SF_D(
    WPP_GLOBAL_Control->AttachedDevice,
    v7,
    v9,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    90,
    (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
    v8);
  if ( v5 )
  {
    ExReleasePushLockExclusiveEx(v5, 0);
    KeLeaveCriticalRegion();
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140005180  push    rbx
0x140005182  push    rbp
0x140005183  push    rsi
0x140005184  push    rdi
0x140005185  push    r13
0x140005187  push    r14
0x140005189  push    r15
0x14000518b  sub     rsp, 50h
0x14000518f  mov     rbp, rdx
0x140005192  mov     r14, rcx
0x140005195  xor     ebx, ebx
0x140005197  mov     rcx, cs:WPP_GLOBAL_Control
0x14000519e  lea     esi, [rbx+1]
0x1400051a1  lea     r15d, [rbx+4]
0x1400051a5  mov     eax, [rcx+2Ch]
0x1400051a8  test    al, 8
0x1400051aa  jz      short loc_1400051B7
0x1400051ac  cmp     [rcx+29h], r15b
0x1400051b0  jb      short loc_1400051B7
0x1400051b2  mov     dl, sil
0x1400051b5  jmp     short loc_1400051B9
0x1400051b7  xor     dl, dl
0x1400051b9  movzx   eax, word ptr [rbp+4]
0x1400051bd  lea     r13, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x1400051c4  mov     r9, [rcx+40h]
0x1400051c8  mov     rcx, [rcx+18h]
0x1400051cc  mov     [rsp+88h+var_40], ax
0x1400051d1  mov     [rsp+88h+var_48], r14
0x1400051d6  mov     [rsp+88h+var_50], r13
0x1400051db  mov     [rsp+88h+var_58], 53h ; 'S'
0x1400051e2  mov     [rsp+88h+var_60], r15d
0x1400051e7  call    WPP_RECORDER_AND_TRACE_SF_qH
0x1400051ec  mov     r8d, 8; unsigned int
0x1400051f2  mov     rdx, rbp; void *
0x1400051f5  mov     rcx, r14; struct _BTDEVICE *
0x1400051f8  call    ?BthUsb_ScoBasicValidation@@YAJPEAU_BTDEVICE@@PEAXK@Z; BthUsb_ScoBasicValidation(_BTDEVICE *,void *,ulong)
0x1400051fd  mov     edi, eax
0x1400051ff  test    eax, eax
0x140005201  js      loc_1400054D6
0x140005207  mov     r13d, 0FFFFh
0x14000520d  cmp     r13w, [rbp+4]
0x140005212  jnz     short loc_140005263
0x140005214  mov     rcx, cs:WPP_GLOBAL_Control
0x14000521b  mov     eax, [rcx+2Ch]
0x14000521e  test    al, 8
0x140005220  jz      short loc_14000522D
0x140005222  cmp     byte ptr [rcx+29h], 2
0x140005226  jb      short loc_14000522D
0x140005228  mov     dl, sil
0x14000522b  jmp     short loc_14000522F
0x14000522d  xor     dl, dl
0x14000522f  lea     r13, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140005236  mov     [rsp+88h+var_50], r13
0x14000523b  mov     [rsp+88h+var_58], 54h ; 'T'
0x140005242  mov     r9, [rcx+40h]
0x140005246  mov     rcx, [rcx+18h]
0x14000524a  mov     [rsp+88h+var_60], r15d
0x14000524f  mov     [rsp+88h+var_68], 2
0x140005254  call    WPP_RECORDER_AND_TRACE_SF_
0x140005259  mov     edi, 0C000000Dh
0x14000525e  jmp     loc_1400054D6
0x140005263  mov     rdi, [r14]
0x140005266  lea     rbx, [rdi+130h]
0x14000526d  call    cs:__imp_KeEnterCriticalRegion
0x140005274  nop     dword ptr [rax+rax+00h]
0x140005279  xor     edx, edx
0x14000527b  mov     rcx, rbx
0x14000527e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140005285  nop     dword ptr [rax+rax+00h]
0x14000528a  movzx   r8d, word ptr [rbp+4]
0x14000528f  xor     edx, edx
0x140005291  movzx   eax, dx
0x140005294  imul    r14, rax, 98h
0x14000529b  add     r14, 2B0h
0x1400052a2  add     r14, rdi
0x1400052a5  cmp     [r14], r8w
0x1400052a9  jz      short loc_1400052B6
0x1400052ab  add     dx, si
0x1400052ae  cmp     dx, 3
0x1400052b2  jb      short loc_140005291
0x1400052b4  jmp     short loc_1400052BB
0x1400052b6  test    r14, r14
0x1400052b9  jnz     short loc_1400052EE
0x1400052bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400052c2  mov     eax, [rcx+2Ch]
0x1400052c5  test    al, 8
0x1400052c7  jz      short loc_1400052D4
0x1400052c9  cmp     byte ptr [rcx+29h], 2
0x1400052cd  jb      short loc_1400052D4
0x1400052cf  mov     dl, sil
0x1400052d2  jmp     short loc_1400052D6
0x1400052d4  xor     dl, dl
0x1400052d6  lea     r13, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x1400052dd  mov     [rsp+88h+var_50], r13
0x1400052e2  mov     [rsp+88h+var_58], 55h ; 'U'
0x1400052e9  jmp     loc_140005242
0x1400052ee  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400052f1  call    ?BthUsb_ScoStopUsbTraffic@@YAXPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoStopUsbTraffic(_DEVICE_EXTENSION *)
0x1400052f6  mov     [r14], r13w
0x1400052fa  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400052fd  add     [rdi+2ACh], r13w
0x140005305  call    ?BthUsb_ScoUpdateChannelsInfo@@YAXPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoUpdateChannelsInfo(_DEVICE_EXTENSION *)
0x14000530a  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x14000530d  call    ?BthUsb_ScoUpdateWriteResources@@YAXPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoUpdateWriteResources(_DEVICE_EXTENSION *)
0x140005312  movzx   r11d, word ptr [rdi+2ACh]
0x14000531a  xor     eax, eax
0x14000531c  cmp     ax, r11w
0x140005320  jnz     loc_1400053F1
0x140005326  mov     rcx, cs:WPP_GLOBAL_Control
0x14000532d  mov     eax, [rcx+2Ch]
0x140005330  test    al, 8
0x140005332  jz      short loc_14000533F
0x140005334  cmp     [rcx+29h], r15b
0x140005338  jb      short loc_14000533F
0x14000533a  mov     dl, sil
0x14000533d  jmp     short loc_140005341
0x14000533f  xor     dl, dl
0x140005341  mov     r9, [rcx+40h]
0x140005345  lea     r13, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x14000534c  mov     rcx, [rcx+18h]
0x140005350  mov     [rsp+88h+var_50], r13
0x140005355  mov     [rsp+88h+var_58], 56h ; 'V'
0x14000535c  mov     [rsp+88h+var_60], r15d
0x140005361  mov     [rsp+88h+var_68], r15b
0x140005366  call    WPP_RECORDER_AND_TRACE_SF_
0x14000536b  xor     edx, edx; struct _USB_INTERFACE_DESCRIPTOR *
0x14000536d  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140005370  call    ?BthUsb_ScoSelectInterface@@YAJPEAU_DEVICE_EXTENSION@@PEAU_USB_INTERFACE_DESCRIPTOR@@@Z; BthUsb_ScoSelectInterface(_DEVICE_EXTENSION *,_USB_INTERFACE_DESCRIPTOR *)
0x140005375  test    eax, eax
0x140005377  jns     short loc_1400053B7
0x140005379  mov     rcx, cs:WPP_GLOBAL_Control
0x140005380  mov     eax, [rcx+2Ch]
0x140005383  test    al, 8
0x140005385  jz      short loc_140005392
0x140005387  cmp     byte ptr [rcx+29h], 2
0x14000538b  jb      short loc_140005392
0x14000538d  mov     dl, sil
0x140005390  jmp     short loc_140005394
0x140005392  xor     dl, dl
0x140005394  mov     r9, [rcx+40h]
0x140005398  mov     rcx, [rcx+18h]
0x14000539c  mov     [rsp+88h+var_50], r13
0x1400053a1  mov     [rsp+88h+var_58], 57h ; 'W'
0x1400053a8  mov     [rsp+88h+var_60], r15d
0x1400053ad  mov     [rsp+88h+var_68], 2
0x1400053b2  call    WPP_RECORDER_AND_TRACE_SF_
0x1400053b7  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400053ba  call    ?BthUsb_ScoFreeReadResources@@YAXPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoFreeReadResources(_DEVICE_EXTENSION *)
0x1400053bf  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400053c2  call    ?BthUsb_ScoFreeWriteResources@@YAXPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoFreeWriteResources(_DEVICE_EXTENSION *)
0x1400053c7  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400053ca  call    ?BthUsb_ScoReleaseUsbBusInterface@@_Y2PAGE@@AXPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoReleaseUsbBusInterface(_DEVICE_EXTENSION *)
0x1400053cf  lea     rcx, [rdi+30h]; RemoveLock
0x1400053d3  mov     r8d, 20h ; ' '; RemlockSize
0x1400053d9  lea     rdx, ?BthUsb_ScoAddChannel@@YAJPEAU_BTDEVICE@@PEAU_BTH_SCO_ADD_CHANNEL_ARG@@@Z; Tag
0x1400053e0  call    cs:__imp_IoReleaseRemoveLockEx
0x1400053e7  nop     dword ptr [rax+rax+00h]
0x1400053ec  jmp     loc_1400054D4
0x1400053f1  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400053f4  call    ?BthUsb_ScoGetMaxUsedBw@@YAKPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoGetMaxUsedBw(_DEVICE_EXTENSION *)
0x1400053f9  mov     r10d, eax
0x1400053fc  xor     r8d, r8d; unsigned int *
0x1400053ff  mov     eax, 10624DD3h
0x140005404  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140005407  mul     r10d
0x14000540a  shr     edx, 6
0x14000540d  imul    edx, r11d
0x140005411  add     edx, esi; unsigned int
0x140005413  call    ?BthUsb_ScoFindInterfaceByFrame@@YAPEAU_USB_INTERFACE_DESCRIPTOR@@PEAU_DEVICE_EXTENSION@@KPEAK@Z; BthUsb_ScoFindInterfaceByFrame(_DEVICE_EXTENSION *,ulong,ulong *)
0x140005418  mov     rbp, rax
0x14000541b  test    rax, rax
0x14000541e  jz      short loc_14000548F
0x140005420  mov     rdx, rax; struct _USB_INTERFACE_DESCRIPTOR *
0x140005423  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140005426  call    ?BthUsb_ScoSelectInterface@@YAJPEAU_DEVICE_EXTENSION@@PEAU_USB_INTERFACE_DESCRIPTOR@@@Z; BthUsb_ScoSelectInterface(_DEVICE_EXTENSION *,_USB_INTERFACE_DESCRIPTOR *)
0x14000542b  test    eax, eax
0x14000542d  js      short loc_140005443
0x14000542f  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140005432  call    ?BthUsb_ScoStartUsbTraffic@@YAXPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoStartUsbTraffic(_DEVICE_EXTENSION *)
0x140005437  lea     r13, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x14000543e  jmp     loc_1400054D4
0x140005443  mov     rcx, cs:WPP_GLOBAL_Control
0x14000544a  mov     eax, [rcx+2Ch]
0x14000544d  test    al, 8
0x14000544f  jz      short loc_14000545C
0x140005451  cmp     byte ptr [rcx+29h], 2
0x140005455  jb      short loc_14000545C
0x140005457  mov     dl, sil
0x14000545a  jmp     short loc_14000545E
0x14000545c  xor     dl, dl
0x14000545e  mov     r9, [rcx+40h]
0x140005462  lea     r13, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140005469  mov     rcx, [rcx+18h]
0x14000546d  mov     [rsp+88h+var_48], rbp
0x140005472  mov     [rsp+88h+var_50], r13
0x140005477  mov     [rsp+88h+var_58], 58h ; 'X'
0x14000547e  mov     [rsp+88h+var_60], r15d
0x140005483  mov     [rsp+88h+var_68], 2
0x140005488  call    WPP_RECORDER_AND_TRACE_SF_q
0x14000548d  jmp     short loc_1400054D4
0x14000548f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005496  mov     eax, [rcx+2Ch]
0x140005499  test    al, 8
0x14000549b  jz      short loc_1400054A8
0x14000549d  cmp     byte ptr [rcx+29h], 2
0x1400054a1  jb      short loc_1400054A8
0x1400054a3  mov     dl, sil
0x1400054a6  jmp     short loc_1400054AA
0x1400054a8  xor     dl, dl
0x1400054aa  mov     r9, [rcx+40h]
0x1400054ae  lea     r13, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x1400054b5  mov     rcx, [rcx+18h]
0x1400054b9  mov     [rsp+88h+var_50], r13
0x1400054be  mov     [rsp+88h+var_58], 59h ; 'Y'
0x1400054c5  mov     [rsp+88h+var_60], r15d
0x1400054ca  mov     [rsp+88h+var_68], 2
0x1400054cf  call    WPP_RECORDER_AND_TRACE_SF_
0x1400054d4  xor     edi, edi
0x1400054d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400054dd  mov     eax, [rcx+2Ch]
0x1400054e0  test    al, 8
0x1400054e2  jz      short loc_1400054EA
0x1400054e4  cmp     [rcx+29h], r15b
0x1400054e8  jnb     short loc_1400054ED
0x1400054ea  xor     sil, sil
0x1400054ed  mov     r9, [rcx+40h]
0x1400054f1  mov     dl, sil
0x1400054f4  mov     rcx, [rcx+18h]
0x1400054f8  mov     dword ptr [rsp+88h+var_48], edi
0x1400054fc  mov     [rsp+88h+var_50], r13
0x140005501  mov     [rsp+88h+var_58], 5Ah ; 'Z'
0x140005508  mov     [rsp+88h+var_60], r15d
0x14000550d  mov     [rsp+88h+var_68], r15b
0x140005512  call    WPP_RECORDER_AND_TRACE_SF_D
0x140005517  test    rbx, rbx
0x14000551a  jz      short loc_140005539
0x14000551c  xor     edx, edx
0x14000551e  mov     rcx, rbx
0x140005521  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140005528  nop     dword ptr [rax+rax+00h]
0x14000552d  call    cs:__imp_KeLeaveCriticalRegion
0x140005534  nop     dword ptr [rax+rax+00h]
0x140005539  mov     eax, edi
0x14000553b  add     rsp, 50h
0x14000553f  pop     r15
0x140005541  pop     r14
0x140005543  pop     r13
0x140005545  pop     rdi
0x140005546  pop     rsi
0x140005547  pop     rbp
0x140005548  pop     rbx
0x140005549  retn
```
