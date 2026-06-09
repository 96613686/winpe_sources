# AudioQueueClient_CreateTransferBrb

- ea: `0x140011714`
- end: `0x14001198e`
- name: `AudioQueueClient_CreateTransferBrb`
- size: `634`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14002f080`

## callees

- `0x14000affc`
- `0x140011714`
- `0x1400155bc`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall AudioQueueClient_CreateTransferBrb(__int64 a1, void *a2, ULONG a3, struct WDFREQUEST__ **a4)
{
  ULONG *v8; // r15
  __int64 v9; // rax
  __int64 v10; // r14
  __int64 v11; // rax
  struct _BRB *v12; // rbx
  int v13; // esi
  ULONG v14; // eax
  char v15; // di
  struct WDFREQUEST__ *v16; // rsi
  int v17; // edx
  int v18; // r8d
  struct WDFREQUEST__ *v19; // rdx
  int v21; // [rsp+20h] [rbp-59h]
  struct WDFREQUEST__ *v22; // [rsp+50h] [rbp-29h] BYREF
  __int128 v23; // [rsp+58h] [rbp-21h] BYREF
  __int128 v24; // [rsp+68h] [rbp-11h]
  __int128 v25; // [rsp+78h] [rbp-1h]
  __int64 *v26; // [rsp+88h] [rbp+Fh]

  v8 = *(ULONG **)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                    WdfDriverGlobals,
                    a1,
                    off_1400221A0);
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1256))(WdfDriverGlobals, a1);
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
          WdfDriverGlobals,
          v9,
          off_140022150);
  v23 = 0;
  v26 = 0;
  v24 = 0;
  v22 = 0;
  v25 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v10 + 8) + 32LL))(517, *(unsigned int *)(v10 + 24));
  v12 = (struct _BRB *)v11;
  if ( v11 )
  {
    *(_QWORD *)(v11 + 112) = *(_QWORD *)(v10 + 16);
    *(_QWORD *)(v11 + 120) = *(_QWORD *)(v10 + 128);
    v14 = *v8;
    v12->BrbL2caRegisterServer.IndicationCallbackContext = a2;
    v15 = 1;
    v12->BrbL2caAclTransfer.TransferFlags = v14;
    v12->BrbL2caAclTransfer.BufferSize = a3;
    v12->BrbL2caRegisterServer.ReferenceObject = 0;
    *(_QWORD *)&v24 = 0;
    v26 = off_1400223F0;
    v23 = 0;
    LODWORD(v23) = 56;
    v25 = 0;
    *((_QWORD *)&v24 + 1) = 0x100000001LL;
    *(_QWORD *)&v25 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1256))(
                        WdfDriverGlobals,
                        a1);
    *((_QWORD *)&v23 + 1) = guard_check_icall_nop;
    v13 = WdfIoTargetCreateAndFormatRequestForBrb(
            (__int64)&v23,
            *(struct WDFIOTARGET__ **)v10,
            *(struct _BTH_PROFILE_DRIVER_INTERFACE **)(v10 + 8),
            v12,
            &v22);
    if ( v13 < 0 )
    {
      v19 = v22;
    }
    else
    {
      v12 = 0;
      v16 = v22;
      *(_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *, __int64 *))(WdfFunctions_01015
                                                                                                  + 1616))(
                   WdfDriverGlobals,
                   v22,
                   off_1400223F0) = v8;
      LOBYTE(v17) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        v15 = 0;
      if ( (_BYTE)v17 || v15 )
      {
        LOBYTE(v18) = v15;
        WPP_RECORDER_AND_TRACE_SF_qd(
          WPP_GLOBAL_Control->AttachedDevice,
          v17,
          v18,
          WPP_GLOBAL_Control->DeviceExtension,
          v21);
      }
      *a4 = v16;
      v19 = 0;
      v13 = 0;
    }
    if ( v19 )
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
    if ( v12 )
      (*(void (__fastcall **)(struct _BRB *))(*(_QWORD *)(v10 + 8) + 40LL))(v12);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140011714  push    rbp
0x140011716  push    rbx
0x140011717  push    rsi
0x140011718  push    rdi
0x140011719  push    r12
0x14001171b  push    r13
0x14001171d  push    r14
0x14001171f  push    r15
0x140011721  lea     rbp, [rsp-1Fh]
0x140011726  sub     rsp, 98h
0x14001172d  mov     rax, cs:WdfFunctions_01015
0x140011734  mov     rdi, rdx
0x140011737  mov     r12, r8
0x14001173a  mov     rsi, rcx
0x14001173d  mov     r8, cs:off_1400221A0
0x140011744  mov     rdx, rcx
0x140011747  mov     rcx, cs:WdfDriverGlobals
0x14001174e  mov     r13, r9
0x140011751  mov     rax, [rax+650h]
0x140011758  call    _guard_dispatch_icall
0x14001175d  mov     rcx, cs:WdfDriverGlobals
0x140011764  mov     rdx, rsi
0x140011767  mov     r15, [rax]
0x14001176a  mov     rax, cs:WdfFunctions_01015
0x140011771  mov     rax, [rax+4E8h]
0x140011778  call    _guard_dispatch_icall
0x14001177d  mov     rcx, cs:WdfFunctions_01015
0x140011784  mov     rdx, rax
0x140011787  mov     r8, cs:off_140022150
0x14001178e  mov     r9, [rcx+650h]
0x140011795  mov     rcx, cs:WdfDriverGlobals
0x14001179c  mov     rax, r9
0x14001179f  call    _guard_dispatch_icall
0x1400117a4  mov     r14, rax
0x1400117a7  xorps   xmm0, xmm0
0x1400117aa  xor     eax, eax
0x1400117ac  movups  [rbp+57h+var_78], xmm0
0x1400117b0  mov     [rbp+57h+var_48], rax
0x1400117b4  movups  [rbp+57h+var_68], xmm0
0x1400117b8  mov     [rbp+57h+var_80], rax
0x1400117bc  movups  [rbp+57h+var_58], xmm0
0x1400117c0  mov     rcx, [r14+8]
0x1400117c4  mov     edx, [r14+18h]
0x1400117c8  mov     rax, [rcx+20h]
0x1400117cc  mov     ecx, 205h
0x1400117d1  call    _guard_dispatch_icall
0x1400117d6  mov     rbx, rax
0x1400117d9  test    rax, rax
0x1400117dc  jnz     short loc_1400117E8
0x1400117de  mov     esi, 0C000009Ah
0x1400117e3  jmp     loc_140011977
0x1400117e8  mov     rax, [r14+10h]
0x1400117ec  xorps   xmm0, xmm0
0x1400117ef  mov     [rbx+70h], rax
0x1400117f3  mov     rdx, rsi
0x1400117f6  mov     rax, [r14+80h]
0x1400117fd  mov     [rbx+78h], rax
0x140011801  mov     eax, [r15]
0x140011804  mov     [rbx+88h], rdi
0x14001180b  mov     edi, 1
0x140011810  mov     [rbx+80h], eax
0x140011816  mov     [rbx+84h], r12d
0x14001181d  mov     qword ptr [rbx+90h], 0
0x140011828  mov     rax, cs:off_1400223F0
0x14001182f  mov     rcx, cs:WdfDriverGlobals
0x140011836  movups  [rbp+57h+var_68], xmm0
0x14001183a  mov     [rbp+57h+var_48], rax
0x14001183e  mov     rax, cs:WdfFunctions_01015
0x140011845  movups  [rbp+57h+var_78], xmm0
0x140011849  mov     dword ptr [rbp+57h+var_78], 38h ; '8'
0x140011850  movups  [rbp+57h+var_58], xmm0
0x140011854  mov     dword ptr [rbp+57h+var_68+8], edi
0x140011857  mov     dword ptr [rbp+57h+var_68+0Ch], edi
0x14001185a  mov     rax, [rax+4E8h]
0x140011861  call    _guard_dispatch_icall
0x140011866  mov     qword ptr [rbp+57h+var_58], rax
0x14001186a  lea     rcx, [rbp+57h+var_78]
0x14001186e  lea     rax, _guard_check_icall_nop
0x140011875  mov     r9, rbx
0x140011878  mov     qword ptr [rbp+57h+var_78+8], rax
0x14001187c  lea     rax, [rbp+57h+var_80]
0x140011880  mov     r8, [r14+8]
0x140011884  mov     rdx, [r14]
0x140011887  mov     qword ptr [rsp+0D0h+var_B0], rax
0x14001188c  call    WdfIoTargetCreateAndFormatRequestForBrb
0x140011891  mov     esi, eax
0x140011893  test    eax, eax
0x140011895  js      loc_14001193F
0x14001189b  mov     rax, cs:WdfFunctions_01015
0x1400118a2  xor     ebx, ebx
0x1400118a4  mov     rsi, [rbp+57h+var_80]
0x1400118a8  mov     r8, cs:off_1400223F0
0x1400118af  mov     rdx, rsi
0x1400118b2  mov     rcx, cs:WdfDriverGlobals
0x1400118b9  mov     rax, [rax+650h]
0x1400118c0  call    _guard_dispatch_icall
0x1400118c5  mov     [rax], r15
0x1400118c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400118cf  lea     rax, WPP_GLOBAL_Control
0x1400118d6  cmp     rcx, rax
0x1400118d9  jz      short loc_1400118F0
0x1400118db  mov     eax, [rcx+2Ch]
0x1400118de  test    al, 10h
0x1400118e0  jz      short loc_1400118F0
0x1400118e2  cmp     byte ptr [rcx+29h], 5
0x1400118e6  jb      short loc_1400118F0
0x1400118e8  mov     dl, dil
0x1400118eb  xor     r15d, r15d
0x1400118ee  jmp     short loc_1400118F6
0x1400118f0  xor     r15d, r15d
0x1400118f3  mov     dl, r15b
0x1400118f6  lea     rax, WPP_RECORDER_INITIALIZED
0x1400118fd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140011904  jz      short loc_14001190D
0x140011906  cmp     [rcx+48h], r15w
0x14001190b  jnz     short loc_140011910
0x14001190d  mov     dil, r15b
0x140011910  test    dl, dl
0x140011912  jnz     short loc_140011919
0x140011914  test    dil, dil
0x140011917  jz      short loc_140011933
0x140011919  mov     r9, [rcx+40h]
0x14001191d  mov     r8b, dil
0x140011920  mov     rcx, [rcx+18h]
0x140011924  mov     [rsp+0D0h+var_88], r12d
0x140011929  mov     [rsp+0D0h+var_90], rsi
0x14001192e  call    WPP_RECORDER_AND_TRACE_SF_qd
0x140011933  mov     [r13+0], rsi
0x140011937  mov     rdx, r15
0x14001193a  mov     esi, r15d
0x14001193d  jmp     short loc_140011943
0x14001193f  mov     rdx, [rbp+57h+var_80]
0x140011943  test    rdx, rdx
0x140011946  jz      short loc_140011962
0x140011948  mov     rax, cs:WdfFunctions_01015
0x14001194f  mov     rcx, cs:WdfDriverGlobals
0x140011956  mov     rax, [rax+680h]
0x14001195d  call    _guard_dispatch_icall
0x140011962  test    rbx, rbx
0x140011965  jz      short loc_140011977
0x140011967  mov     rax, [r14+8]
0x14001196b  mov     rcx, rbx
0x14001196e  mov     rax, [rax+28h]
0x140011972  call    _guard_dispatch_icall
0x140011977  mov     eax, esi
0x140011979  add     rsp, 98h
0x140011980  pop     r15
0x140011982  pop     r14
0x140011984  pop     r13
0x140011986  pop     r12
0x140011988  pop     rdi
0x140011989  pop     rsi
0x14001198a  pop     rbx
0x14001198b  pop     rbp
0x14001198c  retn
```
