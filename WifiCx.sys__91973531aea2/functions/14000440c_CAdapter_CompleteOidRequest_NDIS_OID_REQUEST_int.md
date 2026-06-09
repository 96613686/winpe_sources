# CAdapter::CompleteOidRequest(_NDIS_OID_REQUEST *,int)

- ea: `0x14000440c`
- end: `0x14000468b`
- name: `?CompleteOidRequest@CAdapter@@QEAAXPEAU_NDIS_OID_REQUEST@@H@Z`
- size: `639`
- prototype: `void __fastcall(CAdapter *__hidden this, struct _NDIS_OID_REQUEST *, int)`
- caller_count: `28`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001ed80`
- `0x14002eee0`
- `0x14004ff00`
- `0x140050010`
- `0x14006015c`
- `0x14006a7b0`
- `0x14006d6b0`
- `0x14006d910`
- `0x14006d9e0`
- `0x1400757c0`
- `0x14007c680`
- `0x14007c9d0`
- `0x140080e40`
- `0x140091bf0`
- `0x14009e370`
- `0x14009eb30`
- `0x1400af160`
- `0x1400af270`
- `0x1400af4c0`
- `0x1400ba490`
- `0x1400bbe10`
- `0x1400be770`
- `0x1400be840`
- `0x1400c2900`
- `0x1400c2ad0`
- `0x1400c2de0`
- `0x1400c2eb0`
- `0x1400c62b0`

## callees

- `0x14000440c`
- `0x140004d48`
- `0x14000c778`
- `0x14001efb8`
- `0x14002ed50`
- `0x1400347b4`
- `0x14004bab0`
- `0x1400d02ac`
- `0x1400dfd40`

## pseudocode

```c
void __fastcall CAdapter::CompleteOidRequest(CAdapter *this, struct _NDIS_OID_REQUEST *a2, unsigned int a3)
{
  unsigned int v4; // ebp
  __int64 i; // rdx
  __int64 v7; // rdi
  wificx::utils *v8; // rcx
  unsigned __int64 SystemTime; // rax
  __int64 j; // rcx
  __int64 v11; // rdx
  void *v12; // rdi
  int v13; // edx
  __int64 v14; // rcx
  int v15; // r8d
  NDIS_REQUEST_TYPE RequestType; // eax
  NDIS_OID Oid; // eax
  int v18; // edx
  int v19; // r8d
  __int64 k; // rcx
  __int64 v21; // rdi
  int v22; // edx
  __int64 v23; // [rsp+28h] [rbp-60h]

  v4 = a3;
  for ( i = 0; (unsigned int)i < 6; i = (unsigned int)(i + 1) )
  {
    v7 = *((_QWORD *)this + i + 592);
    if ( v7 && *(_DWORD *)(v7 + 144) == a2->PortNumber )
    {
      if ( *(struct _NDIS_OID_REQUEST **)(v7 + 632) == a2 )
      {
        *(_QWORD *)(v7 + 632) = 0;
        *(_DWORD *)(v7 + 644) = a3;
        *(_QWORD *)(v7 + 656) = CSystem::get_CurrentTime();
      }
      break;
    }
  }
  *((_QWORD *)this + 267) = 0;
  *((_DWORD *)this + 537) = v4;
  if ( (unsigned int)Feature_55721363__private_IsEnabledDeviceUsageNoInline(this) )
    SystemTime = wificx::utils::QuerySystemTime(v8);
  else
    SystemTime = MEMORY[0xFFFFF78000000014];
  *((_QWORD *)this + 270) = SystemTime;
  for ( j = 0; ; j = (unsigned int)(j + 1) )
  {
    if ( (unsigned int)j >= 6 )
    {
      v12 = 0;
      goto LABEL_19;
    }
    v11 = *((_QWORD *)this + j + 592);
    if ( v11 )
    {
      if ( *(_DWORD *)(v11 + 144) == a2->PortNumber )
        break;
    }
  }
  v12 = *(void **)(v11 + 104);
  if ( v12 )
    goto LABEL_20;
LABEL_19:
  __int2c();
LABEL_20:
  if ( !(unsigned int)Feature_55721363__private_IsEnabledDeviceUsageNoInline(j)
    && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_Dddq(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      v15,
      33,
      (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids,
      a2->DATA.QUERY_INFORMATION.Oid,
      a2->PortNumber,
      v4,
      (char)v12);
  }
  if ( *((_DWORD *)this + 1341) )
  {
    RequestType = a2->RequestType;
    if ( RequestType == NdisRequestSetInformation || RequestType == NdisRequestMethod )
    {
      Oid = a2->DATA.QUERY_INFORMATION.Oid;
      if ( Oid == 66088 || Oid == 235143426 || Oid == -50265845 || Oid == -50265841 )
        v4 = 0;
    }
  }
  if ( (unsigned int)Feature_55721363__private_IsEnabledDeviceUsageNoInline(v14) )
  {
    for ( k = 0; (unsigned int)k < 6; k = (unsigned int)(k + 1) )
    {
      v21 = *((_QWORD *)this + k + 592);
      if ( v21 && *(_DWORD *)(v21 + 144) == a2->PortNumber )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_Dddq(
            WPP_GLOBAL_Control->DeviceExtension,
            v18,
            v19,
            411,
            (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
            a2->DATA.QUERY_INFORMATION.Oid,
            a2->PortNumber,
            v4,
            *(_QWORD *)(v21 + 88));
        if ( NetClientVersionHigherThanFramework && (unsigned int)NetFunctionCount <= 0x84 )
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER, wchar_t *))(WdfFunctions_01031 + 3616))(
            WdfDriverGlobals,
            WdfDriverGlobals->Driver,
            NetFrameworkExtensionName);
        else
          ((void (__fastcall *)(PNET_DRIVER_GLOBALS, _QWORD, struct _NDIS_OID_REQUEST *, _QWORD))qword_140110FE0)(
            NetDriverGlobals,
            *(_QWORD *)(v21 + 88),
            a2,
            v4);
        return;
      }
    }
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v22) = 2;
      LODWORD(v23) = a2->PortNumber;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v22,
        1,
        35,
        (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids,
        v23);
    }
  }
  else
  {
    WxNdisMOidRequestComplete(v12, a2, v4, 0);
  }
}

```

## disassembly

```asm
0x14000440c  push    rbx
0x14000440e  push    rbp
0x14000440f  push    rsi
0x140004410  push    rdi
0x140004411  push    r13
0x140004413  push    r15
0x140004415  sub     rsp, 58h
0x140004419  mov     rbx, rdx
0x14000441c  mov     ebp, r8d
0x14000441f  xor     edx, edx
0x140004421  mov     rsi, rcx
0x140004424  cmp     edx, 6
0x140004427  jnb     short loc_14000446B
0x140004429  mov     rdi, [rcx+rdx*8+1280h]
0x140004431  test    rdi, rdi
0x140004434  jz      short loc_140004441
0x140004436  mov     eax, [rbx+8]
0x140004439  cmp     [rdi+90h], eax
0x14000443f  jz      short loc_140004445
0x140004441  inc     edx
0x140004443  jmp     short loc_140004424
0x140004445  cmp     [rdi+278h], rbx
0x14000444c  jnz     short loc_14000446B
0x14000444e  mov     qword ptr [rdi+278h], 0
0x140004459  mov     [rdi+284h], ebp
0x14000445f  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x140004464  mov     [rdi+290h], rax
0x14000446b  mov     qword ptr [rsi+858h], 0
0x140004476  mov     [rsi+864h], ebp
0x14000447c  call    Feature_55721363__private_IsEnabledDeviceUsageNoInline
0x140004481  test    eax, eax
0x140004483  jnz     short loc_140004494
0x140004485  mov     rax, 0FFFFF78000000014h
0x14000448f  mov     rax, [rax]
0x140004492  jmp     short loc_140004499
0x140004494  call    ?QuerySystemTime@utils@wificx@@YA_KXZ; wificx::utils::QuerySystemTime(void)
0x140004499  mov     [rsi+870h], rax
0x1400044a0  xor     ecx, ecx
0x1400044a2  cmp     ecx, 6
0x1400044a5  jnb     short loc_1400044CE
0x1400044a7  mov     rdx, [rsi+rcx*8+1280h]
0x1400044af  test    rdx, rdx
0x1400044b2  jz      short loc_1400044BF
0x1400044b4  mov     eax, [rbx+8]
0x1400044b7  cmp     [rdx+90h], eax
0x1400044bd  jz      short loc_1400044C3
0x1400044bf  inc     ecx
0x1400044c1  jmp     short loc_1400044A2
0x1400044c3  mov     rdi, [rdx+68h]
0x1400044c7  test    rdi, rdi
0x1400044ca  jz      short loc_1400044D0
0x1400044cc  jmp     short loc_1400044D2
0x1400044ce  xor     edi, edi
0x1400044d0  int     2Ch; Windows NT - assertion failure
0x1400044d2  call    Feature_55721363__private_IsEnabledDeviceUsageNoInline
0x1400044d7  lea     r13, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x1400044de  lea     r15, WPP_RECORDER_INITIALIZED
0x1400044e5  test    eax, eax
0x1400044e7  jnz     short loc_140004522
0x1400044e9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400044f0  jz      short loc_140004522
0x1400044f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400044f9  lea     r9d, [rax+21h]
0x1400044fd  mov     eax, [rbx+8]
0x140004500  mov     [rsp+88h+var_48], rdi
0x140004505  mov     [rsp+88h+var_50], ebp
0x140004509  mov     rcx, [rcx+40h]
0x14000450d  mov     [rsp+88h+var_58], eax
0x140004511  mov     eax, [rbx+20h]
0x140004514  mov     dword ptr [rsp+88h+var_60], eax
0x140004518  mov     [rsp+88h+var_68], r13
0x14000451d  call    WPP_RECORDER_SF_Dddq
0x140004522  cmp     dword ptr [rsi+14F4h], 0
0x140004529  jz      short loc_140004559
0x14000452b  mov     eax, [rbx+4]
0x14000452e  cmp     eax, 1
0x140004531  jz      short loc_140004538
0x140004533  cmp     eax, 0Ch
0x140004536  jnz     short loc_140004559
0x140004538  mov     eax, [rbx+20h]
0x14000453b  cmp     eax, 10228h
0x140004540  jz      short loc_140004557
0x140004542  cmp     eax, 0E040102h
0x140004547  jz      short loc_140004557
0x140004549  cmp     eax, 0FD01010Bh
0x14000454e  jz      short loc_140004557
0x140004550  cmp     eax, 0FD01010Fh
0x140004555  jnz     short loc_140004559
0x140004557  xor     ebp, ebp
0x140004559  call    Feature_55721363__private_IsEnabledDeviceUsageNoInline
0x14000455e  test    eax, eax
0x140004560  jnz     short loc_140004578
0x140004562  xor     r9d, r9d; this
0x140004565  mov     r8d, ebp; int
0x140004568  mov     rdx, rbx; struct _NDIS_OID_REQUEST *
0x14000456b  mov     rcx, rdi; MiniportAdapterHandle
0x14000456e  call    ?WxNdisMOidRequestComplete@@YAXPEAXPEAU_NDIS_OID_REQUEST@@HPEBVCPort@@@Z; WxNdisMOidRequestComplete(void *,_NDIS_OID_REQUEST *,int,CPort const *)
0x140004573  jmp     loc_14000467D
0x140004578  xor     ecx, ecx
0x14000457a  cmp     ecx, 6
0x14000457d  jnb     loc_140004647
0x140004583  mov     rdi, [rsi+rcx*8+1280h]
0x14000458b  test    rdi, rdi
0x14000458e  jz      short loc_14000459B
0x140004590  mov     eax, [rbx+8]
0x140004593  cmp     [rdi+90h], eax
0x140004599  jz      short loc_14000459F
0x14000459b  inc     ecx
0x14000459d  jmp     short loc_14000457A
0x14000459f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400045a6  jz      short loc_1400045E5
0x1400045a8  mov     rax, [rdi+58h]
0x1400045ac  mov     r9d, 19Bh
0x1400045b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400045b9  mov     [rsp+88h+var_48], rax
0x1400045be  mov     eax, [rbx+8]
0x1400045c1  mov     [rsp+88h+var_50], ebp
0x1400045c5  mov     rcx, [rcx+40h]
0x1400045c9  mov     [rsp+88h+var_58], eax
0x1400045cd  mov     eax, [rbx+20h]
0x1400045d0  mov     dword ptr [rsp+88h+var_60], eax
0x1400045d4  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x1400045db  mov     [rsp+88h+var_68], rax
0x1400045e0  call    WPP_RECORDER_SF_Dddq
0x1400045e5  cmp     cs:NetClientVersionHigherThanFramework, 0
0x1400045ec  jz      short loc_140004628
0x1400045ee  mov     r9d, 84h
0x1400045f4  cmp     cs:NetFunctionCount, r9d
0x1400045fb  ja      short loc_140004628
0x1400045fd  mov     rax, cs:WdfFunctions_01031
0x140004604  mov     rcx, cs:WdfDriverGlobals
0x14000460b  mov     r8, cs:NetFrameworkExtensionName
0x140004612  mov     byte ptr [rsp+88h+var_68], 0
0x140004617  mov     rax, [rax+0E20h]
0x14000461e  mov     rdx, [rcx]
0x140004621  call    _guard_dispatch_icall
0x140004626  jmp     short loc_14000467D
0x140004628  mov     rax, cs:qword_140110FE0
0x14000462f  mov     r9d, ebp
0x140004632  mov     rdx, [rdi+58h]
0x140004636  mov     r8, rbx
0x140004639  mov     rcx, cs:NetDriverGlobals
0x140004640  call    _guard_dispatch_icall
0x140004645  jmp     short loc_14000467D
0x140004647  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000464c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140004653  jz      short loc_14000467D
0x140004655  mov     rcx, cs:WPP_GLOBAL_Control
0x14000465c  mov     r9d, 23h ; '#'
0x140004662  mov     eax, [rbx+8]
0x140004665  mov     dl, 2
0x140004667  mov     dword ptr [rsp+88h+var_60], eax
0x14000466b  mov     [rsp+88h+var_68], r13
0x140004670  mov     rcx, [rcx+40h]
0x140004674  lea     r8d, [r9-22h]
0x140004678  call    WPP_RECORDER_SF_d
0x14000467d  add     rsp, 58h
0x140004681  pop     r15
0x140004683  pop     r13
0x140004685  pop     rdi
0x140004686  pop     rsi
0x140004687  pop     rbp
0x140004688  pop     rbx
0x140004689  retn
```
