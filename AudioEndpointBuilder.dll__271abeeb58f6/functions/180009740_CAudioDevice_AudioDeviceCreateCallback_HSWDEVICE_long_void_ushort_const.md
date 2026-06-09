# CAudioDevice::AudioDeviceCreateCallback(HSWDEVICE__ *,long,void *,ushort const *)

- ea: `0x180009740`
- end: `0x18000997a`
- name: `?AudioDeviceCreateCallback@CAudioDevice@@SAXPEAUHSWDEVICE__@@JPEAXPEBG@Z`
- size: `570`
- prototype: `static void(struct HSWDEVICE__ *, int, void *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009488`
- `0x180009650`
- `0x180009740`
- `0x180009b94`
- `0x18000af84`
- `0x18000d000`
- `0x18000fa80`
- `0x180010da8`
- `0x18005972c`
- `0x180059904`
- `0x180059c54`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800098d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800098de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800098d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800098de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800097c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800097c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009899`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009899`

## string_xrefs

- `0x1800098af`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CAudioDevice::AudioDeviceCreateCallback(
        struct HSWDEVICE__ *a1,
        int a2,
        char *a3,
        const unsigned __int16 *a4)
{
  struct IMMDevice *v8; // rbx
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  int v10; // edx
  int v11; // r8d
  int v12; // esi
  __int64 cotaskmem_string_nothrow; // rax
  __int64 v14; // rdx
  unsigned int v15; // edx
  int v16; // eax
  int v17; // edx
  int v18; // r8d
  int v19; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  LPVOID pv; // [rsp+90h] [rbp+18h] BYREF

  if ( a2 < 0 )
  {
    v8 = (struct IMMDevice *)*((_QWORD *)a3 + 5);
    pv = v8;
    if ( v8 )
      ((void (__fastcall *)(struct IMMDevice *))v8->lpVtbl->AddRef)(v8);
    AEBTelemetry::LogDeviceCreationFailure(a4, v8, 1, (unsigned int)a2);
    goto LABEL_5;
  }
  v9 = (struct _RTL_CRITICAL_SECTION *)(a3 + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)(a3 + 48));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, (_DWORD)a4, (char)a1);
  }
  if ( *((_DWORD *)a3 + 22) )
    goto LABEL_11;
  *((_QWORD *)a3 + 3) = a1;
  cotaskmem_string_nothrow = wil::make_cotaskmem_string_nothrow((wil *)&pv, a4, 0xFFFFFFFFFFFFFFFFuLL);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    a3,
    cotaskmem_string_nothrow);
  if ( pv )
    CoTaskMemFree(pv);
  if ( !*(_QWORD *)a3 )
  {
    v12 = -2147024882;
    v14 = 1795;
    goto LABEL_25;
  }
  v12 = CAudioDevice::FinishAudioDeviceCreation((CAudioDevice *)a3);
  *((_DWORD *)a3 + 22) = 1;
  v15 = *((_DWORD *)a3 + 25);
  if ( v15 != -1 )
  {
    v16 = CAudioDevice::SetOwningSession((CAudioDevice *)a3, v15);
    if ( v16 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_dSq(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v18, v16, (__int64)a4, (char)a1);
      }
    }
    else
    {
      *((_DWORD *)a3 + 25) = -1;
    }
  }
  if ( v12 < 0 )
  {
    v14 = 1817;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)(unsigned int)v12,
      v19);
    if ( v9 )
      LeaveCriticalSection(v9);
    goto LABEL_14;
  }
LABEL_11:
  if ( v9 )
    LeaveCriticalSection(v9);
  v12 = 0;
LABEL_14:
  v8 = (struct IMMDevice *)*((_QWORD *)a3 + 5);
  if ( v12 >= 0 )
  {
    pv = (LPVOID)*((_QWORD *)a3 + 5);
    if ( v8 )
      ((void (__fastcall *)(struct IMMDevice *))v8->lpVtbl->AddRef)(v8);
    AEBTelemetry::LogDeviceTelemetry(v8, a4);
  }
  else
  {
    pv = (LPVOID)*((_QWORD *)a3 + 5);
    if ( v8 )
      ((void (__fastcall *)(struct IMMDevice *))v8->lpVtbl->AddRef)(v8);
    AEBTelemetry::LogDeviceCreationFailure(a4, v8, 2, (unsigned int)v12);
  }
LABEL_5:
  if ( v8 )
    ((void (__fastcall *)(struct IMMDevice *))v8->lpVtbl->Release)(v8);
  CAudioDevice::Release((CAudioDevice *)a3);
}

```

## disassembly

```asm
0x180009740  mov     rax, rsp
0x180009743  push    rbx
0x180009744  push    rbp
0x180009745  push    rsi
0x180009746  push    rdi
0x180009747  push    r13
0x180009749  push    r14
0x18000974b  sub     rsp, 48h
0x18000974f  mov     rbp, r9
0x180009752  mov     rdi, r8
0x180009755  mov     esi, edx
0x180009757  mov     r14, rcx
0x18000975a  test    edx, edx
0x18000975c  jns     short loc_1800097B9
0x18000975e  mov     rbx, [r8+28h]
0x180009762  mov     [rax+18h], rbx
0x180009766  test    rbx, rbx
0x180009769  jz      short loc_18000977B
0x18000976b  mov     rax, [rbx]
0x18000976e  mov     rcx, rbx
0x180009771  mov     rax, [rax+8]
0x180009775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000977a  nop
0x18000977b  mov     r9d, esi
0x18000977e  mov     r8d, 1
0x180009784  mov     rdx, rbx
0x180009787  mov     rcx, rbp
0x18000978a  call    ?LogDeviceCreationFailure@AEBTelemetry@@SAXPEBGPEAUIMMDevice@@W4DeviceCreationFailureSite@@J@Z; AEBTelemetry::LogDeviceCreationFailure(ushort const *,IMMDevice *,DeviceCreationFailureSite,long)
0x18000978f  nop
0x180009790  test    rbx, rbx
0x180009793  jz      short loc_1800097A5
0x180009795  mov     rax, [rbx]
0x180009798  mov     rcx, rbx
0x18000979b  mov     rax, [rax+10h]
0x18000979f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097a4  nop
0x1800097a5  mov     rcx, rdi; this
0x1800097a8  add     rsp, 48h
0x1800097ac  pop     r14
0x1800097ae  pop     r13
0x1800097b0  pop     rdi
0x1800097b1  pop     rsi
0x1800097b2  pop     rbp
0x1800097b3  pop     rbx
0x1800097b4  jmp     ?Release@CAudioDevice@@QEAAKXZ; CAudioDevice::Release(void)
0x1800097b9  lea     rbx, [r8+30h]
0x1800097bd  mov     rcx, rbx; lpCriticalSection
0x1800097c0  call    cs:__imp_EnterCriticalSection
0x1800097c6  mov     [rsp+78h+var_48], rbx
0x1800097cb  lea     r13, WPP_GLOBAL_Control
0x1800097d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097d9  cmp     rcx, r13
0x1800097dc  jz      short loc_1800097EB
0x1800097de  test    dword ptr [rcx+1Ch], 80000h
0x1800097e5  jnz     loc_180009926
0x1800097eb  cmp     dword ptr [rdi+58h], 0
0x1800097ef  jz      short loc_180009869
0x1800097f1  test    rbx, rbx
0x1800097f4  jnz     loc_1800098DB
0x1800097fa  xor     esi, esi
0x1800097fc  mov     rbx, [rdi+28h]
0x180009800  test    esi, esi
0x180009802  jns     short loc_18000983B
0x180009804  mov     [rsp+78h+pv], rbx
0x18000980c  test    rbx, rbx
0x18000980f  jz      short loc_180009821
0x180009811  mov     rax, [rbx]
0x180009814  mov     rcx, rbx
0x180009817  mov     rax, [rax+8]
0x18000981b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009820  nop
0x180009821  mov     r9d, esi
0x180009824  mov     r8d, 2
0x18000982a  mov     rdx, rbx
0x18000982d  mov     rcx, rbp
0x180009830  call    ?LogDeviceCreationFailure@AEBTelemetry@@SAXPEBGPEAUIMMDevice@@W4DeviceCreationFailureSite@@J@Z; AEBTelemetry::LogDeviceCreationFailure(ushort const *,IMMDevice *,DeviceCreationFailureSite,long)
0x180009835  nop
0x180009836  jmp     loc_180009790
0x18000983b  mov     [rsp+78h+pv], rbx
0x180009843  test    rbx, rbx
0x180009846  jz      short loc_180009858
0x180009848  mov     rax, [rbx]
0x18000984b  mov     rcx, rbx
0x18000984e  mov     rax, [rax+8]
0x180009852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009857  nop
0x180009858  mov     rdx, rbp; unsigned __int16 *
0x18000985b  mov     rcx, rbx; struct IMMDevice *
0x18000985e  call    ?LogDeviceTelemetry@AEBTelemetry@@SAXPEAUIMMDevice@@PEBG@Z; AEBTelemetry::LogDeviceTelemetry(IMMDevice *,ushort const *)
0x180009863  nop
0x180009864  jmp     loc_180009790
0x180009869  mov     [rdi+18h], r14
0x18000986d  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180009871  mov     rdx, rbp; unsigned __int16 *
0x180009874  lea     rcx, [rsp+78h+pv]; this
0x18000987c  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180009881  mov     rdx, rax
0x180009884  mov     rcx, rdi
0x180009887  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18000988c  mov     rcx, [rsp+78h+pv]; pv
0x180009894  test    rcx, rcx
0x180009897  jz      short loc_18000989F
0x180009899  call    cs:__imp_CoTaskMemFree
0x18000989f  cmp     qword ptr [rdi], 0
0x1800098a3  jnz     short loc_1800098E9
0x1800098a5  mov     esi, 8007000Eh
0x1800098aa  mov     edx, 703h; void *
0x1800098af  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x1800098b6  mov     r9d, esi; char *
0x1800098b9  mov     rcx, [rsp+78h]; this
0x1800098be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800098c3  nop
0x1800098c4  test    rbx, rbx
0x1800098c7  jz      loc_1800097FC
0x1800098cd  mov     rcx, rbx; lpCriticalSection
0x1800098d0  call    cs:__imp_LeaveCriticalSection
0x1800098d6  jmp     loc_1800097FC
0x1800098db  mov     rcx, rbx; lpCriticalSection
0x1800098de  call    cs:__imp_LeaveCriticalSection
0x1800098e4  jmp     loc_1800097FA
0x1800098e9  mov     rcx, rdi; this
0x1800098ec  call    ?FinishAudioDeviceCreation@CAudioDevice@@AEAAJXZ; CAudioDevice::FinishAudioDeviceCreation(void)
0x1800098f1  mov     esi, eax
0x1800098f3  mov     dword ptr [rdi+58h], 1
0x1800098fa  mov     edx, [rdi+64h]; unsigned int
0x1800098fd  cmp     edx, 0FFFFFFFFh
0x180009900  jnz     short loc_180009911
0x180009902  test    esi, esi
0x180009904  jns     loc_1800097F1
0x18000990a  mov     edx, 719h
0x18000990f  jmp     short loc_1800098AF
0x180009911  mov     rcx, rdi; this
0x180009914  call    ?SetOwningSession@CAudioDevice@@QEAAJK@Z; CAudioDevice::SetOwningSession(ulong)
0x180009919  test    eax, eax
0x18000991b  js      short loc_180009946
0x18000991d  mov     dword ptr [rdi+64h], 0FFFFFFFFh
0x180009924  jmp     short loc_180009902
0x180009926  cmp     byte ptr [rcx+19h], 5
0x18000992a  jb      loc_1800097EB
0x180009930  mov     [rsp+78h+var_58], r14
0x180009935  mov     r9, rbp
0x180009938  mov     rcx, [rcx+10h]
0x18000993c  call    WPP_SF_Sq
0x180009941  jmp     loc_1800097EB
0x180009946  mov     rcx, cs:WPP_GLOBAL_Control
0x18000994d  cmp     rcx, r13
0x180009950  jz      short loc_180009902
0x180009952  test    dword ptr [rcx+1Ch], 80000h
0x180009959  jz      short loc_180009902
0x18000995b  cmp     byte ptr [rcx+19h], 2
0x18000995f  jb      short loc_180009902
0x180009961  mov     [rsp+78h+var_50], r14
0x180009966  mov     [rsp+78h+var_58], rbp
0x18000996b  mov     r9d, eax
0x18000996e  mov     rcx, [rcx+10h]
0x180009972  call    WPP_SF_dSq
0x180009977  jmp     short loc_180009902
```
