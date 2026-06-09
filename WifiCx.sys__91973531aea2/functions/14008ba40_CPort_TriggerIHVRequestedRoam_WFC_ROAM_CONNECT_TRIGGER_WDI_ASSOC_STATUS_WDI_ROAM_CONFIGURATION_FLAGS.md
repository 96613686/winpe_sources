# CPort::TriggerIHVRequestedRoam(_WFC_ROAM_CONNECT_TRIGGER,_WDI_ASSOC_STATUS,_WDI_ROAM_CONFIGURATION_FLAGS)

- ea: `0x14008ba40`
- end: `0x14008bd84`
- name: `?TriggerIHVRequestedRoam@CPort@@QEAAHW4_WFC_ROAM_CONNECT_TRIGGER@@W4_WDI_ASSOC_STATUS@@W4_WDI_ROAM_CONFIGURATION_FLAGS@@@Z`
- size: `836`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x140026010`

## callees

- `0x14000688c`
- `0x14000c778`
- `0x14000d054`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002a9f8`
- `0x14002aaec`
- `0x14002ed50`
- `0x1400683ac`
- `0x14008af8c`
- `0x14008ba40`
- `0x1400dfd40`

## pseudocode

```c
__int64 __fastcall CPort::TriggerIHVRequestedRoam(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned int started; // edi
  unsigned int v6; // ebp
  int v8; // r9d
  CPropertyCache *v9; // rax
  char v10; // dl
  int v11; // eax
  int v12; // edx
  int v13; // r8d
  int v14; // eax
  int v15; // r8d
  int v16; // edx
  unsigned int v17; // eax
  int v18; // edx
  int v19; // edx
  __int64 v21; // [rsp+28h] [rbp-60h]
  __int64 v22; // [rsp+38h] [rbp-50h]
  unsigned __int64 CurrentTime; // [rsp+90h] [rbp+8h] BYREF

  started = 0;
  v6 = a3;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      156,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
  }
  if ( (*(_DWORD *)(a1 + 152) & 0x11) == 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return started;
    v8 = 157;
LABEL_37:
    v10 = 2;
    goto LABEL_38;
  }
  v9 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 8LL) + 8LL))(*(_QWORD *)(a1 + 136) + 8LL);
  if ( CPropertyCache::GetPropertyBooleanOrDefault(v9, 0x3Du, 0) && *(_QWORD *)(a1 + 392) )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return started;
    v8 = 158;
  }
  else if ( *(_QWORD *)(a1 + 80) && (started = 0x1000000, v6 == 0x1000000) )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return started;
    v8 = 159;
  }
  else
  {
    LOBYTE(a3) = 1;
    v11 = CPropertyCache::SetPropertyBoolean((CPropertyCache *)(a1 + 480), 82, a3);
    if ( v11 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        v13,
        160,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        a1,
        *(_WORD *)(a1 + 148),
        v11);
    }
    CurrentTime = CSystem::get_CurrentTime();
    v14 = CPropertyCache::SetPropertyBuffer(
            (CPropertyCache *)(a1 + 480),
            0x53u,
            8u,
            (const unsigned __int8 *)&CurrentTime);
    if ( v14 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v16 = *(unsigned __int16 *)(a1 + 148);
      LODWORD(v22) = v14;
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        v15,
        161,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        a1,
        *(_WORD *)(a1 + 148),
        v22);
    }
    v17 = CPropertyCache::SetPropertyULong((CPropertyCache *)(a1 + 480), 0x54u, v6);
    started = v17;
    if ( v17 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v22) = v17;
      LOBYTE(v18) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v18,
        a3,
        162,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        a1,
        *(_WORD *)(a1 + 148),
        v22);
    }
    if ( !*(_QWORD *)(a1 + 392) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          a3,
          164,
          (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
          a1,
          *(_WORD *)(a1 + 148));
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            5,
            1,
            165,
            (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
        }
      }
      started = CPort::StartRoamJob(a1, (char **)(a1 + 392), 3, v6, a4, 1);
      if ( !started )
        goto LABEL_39;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return started;
      v8 = 166;
      goto LABEL_37;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return started;
    v8 = 163;
  }
  v10 = 4;
LABEL_38:
  WPP_RECORDER_SF_qD(
    WPP_GLOBAL_Control->DeviceExtension,
    v10,
    a3,
    v8,
    (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
    a1,
    *(_WORD *)(a1 + 148));
LABEL_39:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v21) = started;
    LOBYTE(v19) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v19,
      1,
      167,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      v21);
  }
  return started;
}

```

## disassembly

```asm
0x14008ba40  push    rbx
0x14008ba42  push    rbp
0x14008ba43  push    rsi
0x14008ba44  push    rdi
0x14008ba45  push    r12
0x14008ba47  push    r13
0x14008ba49  push    r14
0x14008ba4b  push    r15
0x14008ba4d  sub     rsp, 48h
0x14008ba51  xor     r12d, r12d
0x14008ba54  mov     r14d, r9d
0x14008ba57  mov     edi, r12d
0x14008ba5a  mov     ebp, r8d
0x14008ba5d  mov     rbx, rcx
0x14008ba60  lea     r15, WPP_RECORDER_INITIALIZED
0x14008ba67  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008ba6e  lea     r13, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008ba75  jz      short loc_14008BAA7
0x14008ba77  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ba7e  cmp     byte ptr [rcx+29h], 5
0x14008ba82  jnb     short loc_14008BA8B
0x14008ba84  cmp     [rcx+48h], r12w
0x14008ba89  jz      short loc_14008BAA7
0x14008ba8b  mov     rcx, [rcx+40h]
0x14008ba8f  mov     r9d, 9Ch
0x14008ba95  mov     r8d, 1
0x14008ba9b  mov     [rsp+88h+var_68], r13
0x14008baa0  mov     dl, 5
0x14008baa2  call    WPP_RECORDER_SF_
0x14008baa7  mov     eax, [rbx+98h]
0x14008baad  test    al, 11h
0x14008baaf  jnz     short loc_14008BAC9
0x14008bab1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008bab8  jz      loc_14008BD70
0x14008babe  mov     r9d, 9Dh
0x14008bac4  jmp     loc_14008BD0C
0x14008bac9  mov     rcx, [rbx+88h]
0x14008bad0  add     rcx, 8
0x14008bad4  mov     rax, [rcx]
0x14008bad7  mov     rax, [rax+8]
0x14008badb  call    _guard_dispatch_icall
0x14008bae0  xor     r8d, r8d; unsigned __int8
0x14008bae3  mov     rcx, rax; this
0x14008bae6  lea     edx, [r8+3Dh]; unsigned int
0x14008baea  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x14008baef  test    al, al
0x14008baf1  jz      short loc_14008BB16
0x14008baf3  cmp     [rbx+188h], r12
0x14008bafa  jz      short loc_14008BB16
0x14008bafc  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008bb03  jz      loc_14008BD70
0x14008bb09  mov     r9d, 9Eh
0x14008bb0f  mov     dl, 4
0x14008bb11  jmp     loc_14008BD0E
0x14008bb16  cmp     [rbx+50h], r12
0x14008bb1a  jz      short loc_14008BB3A
0x14008bb1c  mov     edi, 1000000h
0x14008bb21  cmp     ebp, edi
0x14008bb23  jnz     short loc_14008BB3A
0x14008bb25  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008bb2c  jz      loc_14008BD70
0x14008bb32  mov     r9d, 9Fh
0x14008bb38  jmp     short loc_14008BB0F
0x14008bb3a  lea     rdi, [rbx+1E0h]
0x14008bb41  mov     r8b, 1; unsigned __int8
0x14008bb44  mov     rcx, rdi; this
0x14008bb47  mov     edx, 52h ; 'R'; unsigned int
0x14008bb4c  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x14008bb51  test    eax, eax
0x14008bb53  jz      short loc_14008BB8F
0x14008bb55  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008bb5c  jz      short loc_14008BB8F
0x14008bb5e  movzx   ecx, word ptr [rbx+94h]
0x14008bb65  mov     r9d, 0A0h
0x14008bb6b  mov     dword ptr [rsp+88h+var_50], eax
0x14008bb6f  mov     dl, 2
0x14008bb71  mov     [rsp+88h+var_58], ecx
0x14008bb75  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bb7c  mov     [rsp+88h+var_60], rbx
0x14008bb81  mov     [rsp+88h+var_68], r13
0x14008bb86  mov     rcx, [rcx+40h]
0x14008bb8a  call    WPP_RECORDER_SF_qDD
0x14008bb8f  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x14008bb94  mov     edx, 53h ; 'S'; unsigned int
0x14008bb99  mov     [rsp+88h+arg_0], rax
0x14008bba1  lea     r9, [rsp+88h+arg_0]; unsigned __int8 *
0x14008bba9  mov     rcx, rdi; this
0x14008bbac  lea     r8d, [rdx-4Bh]; unsigned int
0x14008bbb0  call    ?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEBE@Z; CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar const *)
0x14008bbb5  test    eax, eax
0x14008bbb7  jz      short loc_14008BBF3
0x14008bbb9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008bbc0  jz      short loc_14008BBF3
0x14008bbc2  movzx   edx, word ptr [rbx+94h]
0x14008bbc9  mov     r9d, 0A1h
0x14008bbcf  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bbd6  mov     dword ptr [rsp+88h+var_50], eax
0x14008bbda  mov     [rsp+88h+var_58], edx
0x14008bbde  mov     dl, 2
0x14008bbe0  mov     [rsp+88h+var_60], rbx
0x14008bbe5  mov     rcx, [rcx+40h]
0x14008bbe9  mov     [rsp+88h+var_68], r13
0x14008bbee  call    WPP_RECORDER_SF_qDD
0x14008bbf3  mov     r8d, ebp; unsigned int
0x14008bbf6  mov     edx, 54h ; 'T'; unsigned int
0x14008bbfb  mov     rcx, rdi; this
0x14008bbfe  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x14008bc03  mov     edi, eax
0x14008bc05  test    eax, eax
0x14008bc07  jz      short loc_14008BC43
0x14008bc09  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008bc10  jz      short loc_14008BC43
0x14008bc12  movzx   ecx, word ptr [rbx+94h]
0x14008bc19  mov     r9d, 0A2h
0x14008bc1f  mov     dword ptr [rsp+88h+var_50], eax
0x14008bc23  mov     dl, 2
0x14008bc25  mov     [rsp+88h+var_58], ecx
0x14008bc29  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bc30  mov     [rsp+88h+var_60], rbx
0x14008bc35  mov     [rsp+88h+var_68], r13
0x14008bc3a  mov     rcx, [rcx+40h]
0x14008bc3e  call    WPP_RECORDER_SF_qDD
0x14008bc43  lea     rsi, [rbx+188h]
0x14008bc4a  cmp     [rsi], r12
0x14008bc4d  jz      short loc_14008BC67
0x14008bc4f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008bc56  jz      loc_14008BD70
0x14008bc5c  mov     r9d, 0A3h
0x14008bc62  jmp     loc_14008BB0F
0x14008bc67  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008bc6e  jz      short loc_14008BCD6
0x14008bc70  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bc77  mov     r9d, 0A4h
0x14008bc7d  movzx   eax, word ptr [rbx+94h]
0x14008bc84  mov     dl, 4
0x14008bc86  mov     [rsp+88h+var_58], eax
0x14008bc8a  mov     [rsp+88h+var_60], rbx
0x14008bc8f  mov     rcx, [rcx+40h]
0x14008bc93  mov     [rsp+88h+var_68], r13
0x14008bc98  call    WPP_RECORDER_SF_qD
0x14008bc9d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008bca4  jz      short loc_14008BCD6
0x14008bca6  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bcad  cmp     byte ptr [rcx+29h], 5
0x14008bcb1  jnb     short loc_14008BCBA
0x14008bcb3  cmp     [rcx+48h], r12w
0x14008bcb8  jz      short loc_14008BCD6
0x14008bcba  mov     rcx, [rcx+40h]
0x14008bcbe  mov     r9d, 0A5h
0x14008bcc4  mov     r8d, 1
0x14008bcca  mov     [rsp+88h+var_68], r13
0x14008bccf  mov     dl, 5
0x14008bcd1  call    WPP_RECORDER_SF_
0x14008bcd6  mov     dword ptr [rsp+88h+var_60], 1
0x14008bcde  mov     r9d, ebp
0x14008bce1  mov     r8d, 3
0x14008bce7  mov     dword ptr [rsp+88h+var_68], r14d
0x14008bcec  mov     rdx, rsi
0x14008bcef  mov     rcx, rbx
0x14008bcf2  call    ?StartRoamJob@CPort@@QEAAHPEAPEAVCRoamReconnectJob@@W4_WFC_ROAM_CONNECT_TRIGGER@@W4_WDI_ASSOC_STATUS@@W4_WDI_ROAM_CONFIGURATION_FLAGS@@W4_WDF_EXECUTION_LEVEL@@@Z; CPort::StartRoamJob(CRoamReconnectJob * *,_WFC_ROAM_CONNECT_TRIGGER,_WDI_ASSOC_STATUS,_WDI_ROAM_CONFIGURATION_FLAGS,_WDF_EXECUTION_LEVEL)
0x14008bcf7  mov     edi, eax
0x14008bcf9  test    eax, eax
0x14008bcfb  jz      short loc_14008BD33
0x14008bcfd  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008bd04  jz      short loc_14008BD70
0x14008bd06  mov     r9d, 0A6h
0x14008bd0c  mov     dl, 2
0x14008bd0e  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bd15  movzx   eax, word ptr [rbx+94h]
0x14008bd1c  mov     [rsp+88h+var_58], eax
0x14008bd20  mov     [rsp+88h+var_60], rbx
0x14008bd25  mov     rcx, [rcx+40h]
0x14008bd29  mov     [rsp+88h+var_68], r13
0x14008bd2e  call    WPP_RECORDER_SF_qD
0x14008bd33  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008bd3a  jz      short loc_14008BD70
0x14008bd3c  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bd43  cmp     byte ptr [rcx+29h], 5
0x14008bd47  jnb     short loc_14008BD50
0x14008bd49  cmp     [rcx+48h], r12w
0x14008bd4e  jz      short loc_14008BD70
0x14008bd50  mov     rcx, [rcx+40h]
0x14008bd54  mov     r9d, 0A7h
0x14008bd5a  mov     dword ptr [rsp+88h+var_60], edi
0x14008bd5e  mov     r8d, 1
0x14008bd64  mov     dl, 5
0x14008bd66  mov     [rsp+88h+var_68], r13
0x14008bd6b  call    WPP_RECORDER_SF_d
0x14008bd70  mov     eax, edi
0x14008bd72  add     rsp, 48h
0x14008bd76  pop     r15
0x14008bd78  pop     r14
0x14008bd7a  pop     r13
0x14008bd7c  pop     r12
0x14008bd7e  pop     rdi
0x14008bd7f  pop     rsi
0x14008bd80  pop     rbp
0x14008bd81  pop     rbx
0x14008bd82  retn
```
