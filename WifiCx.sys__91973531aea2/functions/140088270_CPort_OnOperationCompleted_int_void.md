# CPort::OnOperationCompleted(int,void *)

- ea: `0x140088270`
- end: `0x140088770`
- name: `?OnOperationCompleted@CPort@@UEAAXHPEAX@Z`
- size: `1280`
- prototype: `void __fastcall(CPort *__hidden this, int, void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000688c`
- `0x14000c778`
- `0x14000d054`
- `0x140016d00`
- `0x14001a630`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002bd34`
- `0x14002ed50`
- `0x140088270`
- `0x140088e28`
- `0x14008af8c`
- `0x1400a9d4c`
- `0x1400dfd40`

## pseudocode

```c
void __fastcall CPort::OnOperationCompleted(CPort *this, int a2, _DWORD *a3)
{
  int v4; // ebp
  _WORD *v6; // rbx
  __int64 v7; // rcx
  int PropertyBuffer; // edx
  int v9; // r8d
  unsigned __int64 v10; // rbx
  int v11; // edx
  int v12; // r8d
  _WORD *v13; // rbx
  int v14; // edx
  int PropertyULong; // ecx
  int v16; // r8d
  unsigned int RoamConfig; // eax
  int v18; // r8d
  unsigned int v19; // r9d
  int started; // eax
  int v21; // r8d
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // [rsp+28h] [rbp-60h]
  char v26[8]; // [rsp+38h] [rbp-50h]
  char v27; // [rsp+38h] [rbp-50h]
  unsigned int v28; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v29; // [rsp+A0h] [rbp+18h] BYREF
  unsigned __int8 *v30; // [rsp+A8h] [rbp+20h] BYREF

  v4 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      42,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
  }
  if ( a3 == *((_DWORD **)this + 48) )
  {
    v6 = (_WORD *)((char *)this + 140);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        43,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        (_BYTE)this - 8,
        *v6,
        v4);
    }
    v7 = *((_QWORD *)this + 48);
    if ( v7 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 40LL))(v7, 1);
    *((_QWORD *)this + 48) = 0;
    if ( CPropertyCache::GetPropertyBooleanOrDefault((CPort *)((char *)this + 472), 0x52u, 0) )
    {
      v30 = 0;
      v28 = 0;
      v29 = 0;
      PropertyBuffer = CPropertyCache::GetPropertyBuffer((CPort *)((char *)this + 472), 0x53u, &v28, &v30);
      if ( PropertyBuffer || v28 != 8 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return;
        v27 = PropertyBuffer;
        LOBYTE(PropertyBuffer) = 2;
        WPP_RECORDER_SF_qDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          PropertyBuffer,
          v9,
          48,
          (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
          (_BYTE)this - 8,
          *v6,
          v27,
          v28);
      }
      else
      {
        v10 = *(_QWORD *)v30 + 200000000LL;
        if ( CSystem::get_CurrentTime() >= v10 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return;
          LOBYTE(v11) = 4;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            v11,
            v12,
            47,
            (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
            (_BYTE)this - 8,
            *((_WORD *)this + 70));
        }
        else
        {
          v13 = (_WORD *)((char *)this + 140);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v11) = 4;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v11,
              v12,
              44,
              (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
              (_BYTE)this - 8,
              *v13);
          }
          PropertyULong = CPropertyCache::GetPropertyULong((CPort *)((char *)this + 472), 0x54u, &v29);
          if ( (PropertyULong || v29 == 0xFFFF) && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            *(_DWORD *)v26 = PropertyULong;
            LOBYTE(v14) = 2;
            WPP_RECORDER_SF_qDD(
              WPP_GLOBAL_Control->DeviceExtension,
              v14,
              v16,
              45,
              (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
              (_BYTE)this - 8,
              *v13,
              *(_QWORD *)v26);
            v13 = (_WORD *)((char *)this + 140);
          }
          RoamConfig = CConnectHelpers::GetRoamConfig(3);
          started = CPort::StartRoamJob((__int64)this - 8, (char **)this + 48, v18, v19, RoamConfig, 2);
          if ( started )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              return;
            *(_DWORD *)v26 = started;
            LOBYTE(a2) = 2;
            WPP_RECORDER_SF_qDD(
              WPP_GLOBAL_Control->DeviceExtension,
              a2,
              v21,
              46,
              (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
              (_BYTE)this - 8,
              *v13,
              *(_QWORD *)v26);
          }
        }
      }
    }
  }
  else if ( a3 == *((_DWORD **)this + 49) )
  {
    CPort::OnReconnectCompleted((CPort *)((char *)this - 8), v4);
  }
  else if ( a3 == *((_DWORD **)this + 50) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        49,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        (_BYTE)this - 8,
        *((_WORD *)this + 70),
        v4);
    }
    v22 = *((_QWORD *)this + 50);
    if ( v22 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 40LL))(v22, 1);
    *((_QWORD *)this + 50) = 0;
  }
  else if ( a3 == *((_DWORD **)this + 52) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        50,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        (_BYTE)this - 8,
        *((_WORD *)this + 70),
        v4);
    }
    v23 = *((_QWORD *)this + 52);
    if ( v23 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 40LL))(v23, 1);
    *((_QWORD *)this + 52) = 0;
  }
  else if ( a3 == *((_DWORD **)this + 51) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        51,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        (_BYTE)this - 8,
        *((_WORD *)this + 70),
        v4);
    }
    v24 = *((_QWORD *)this + 51);
    if ( v24 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 40LL))(v24, 1);
    *((_QWORD *)this + 51) = 0;
  }
  else if ( a3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        52,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        (_BYTE)this - 8,
        *((_WORD *)this + 70),
        a3[15],
        v4);
    }
    (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a3 + 40LL))(a3, 1);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v25) = 0;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      53,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      v25);
  }
}

```

## disassembly

```asm
0x140088270  mov     [rsp+arg_8], rbx
0x140088275  push    rbp
0x140088276  push    rsi
0x140088277  push    rdi
0x140088278  push    r12
0x14008827a  push    r13
0x14008827c  push    r14
0x14008827e  push    r15
0x140088280  sub     rsp, 50h
0x140088284  mov     rbx, r8
0x140088287  mov     ebp, edx
0x140088289  mov     rdi, rcx
0x14008828c  lea     r12, WPP_RECORDER_INITIALIZED
0x140088293  xor     r15d, r15d
0x140088296  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14008829d  lea     r13, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x1400882a4  jz      short loc_1400882D4
0x1400882a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400882ad  cmp     byte ptr [rcx+29h], 5
0x1400882b1  jnb     short loc_1400882BA
0x1400882b3  cmp     [rcx+48h], r15w
0x1400882b8  jz      short loc_1400882D4
0x1400882ba  mov     rcx, [rcx+40h]
0x1400882be  mov     r9d, 2Ah ; '*'
0x1400882c4  mov     dl, 5
0x1400882c6  mov     [rsp+88h+var_68], r13
0x1400882cb  lea     r8d, [r9-29h]
0x1400882cf  call    WPP_RECORDER_SF_
0x1400882d4  lea     rsi, [rdi-8]
0x1400882d8  cmp     rbx, [rsi+188h]
0x1400882df  jnz     loc_140088568
0x1400882e5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400882ec  lea     rbx, [rdi+8Ch]
0x1400882f3  jz      short loc_140088322
0x1400882f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400882fc  mov     r9d, 2Bh ; '+'
0x140088302  movzx   eax, word ptr [rbx]
0x140088305  mov     dl, 4
0x140088307  mov     dword ptr [rsp+88h+var_50], ebp
0x14008830b  mov     [rsp+88h+var_58], eax
0x14008830f  mov     rcx, [rcx+40h]
0x140088313  mov     [rsp+88h+var_60], rsi
0x140088318  mov     [rsp+88h+var_68], r13
0x14008831d  call    WPP_RECORDER_SF_qDD
0x140088322  lea     r14, [rdi+180h]
0x140088329  mov     rcx, [r14]
0x14008832c  test    rcx, rcx
0x14008832f  jz      short loc_140088342
0x140088331  mov     rax, [rcx]
0x140088334  mov     edx, 1
0x140088339  mov     rax, [rax+28h]
0x14008833d  call    _guard_dispatch_icall
0x140088342  xor     r8d, r8d; unsigned __int8
0x140088345  mov     [r14], r15
0x140088348  lea     rbp, [rdi+1D8h]
0x14008834f  mov     rcx, rbp; this
0x140088352  lea     edx, [r8+52h]; unsigned int
0x140088356  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x14008835b  test    al, al
0x14008835d  jz      loc_14008871B
0x140088363  lea     r9, [rsp+88h+arg_18]; unsigned __int8 **
0x14008836b  mov     [rsp+88h+arg_18], r15
0x140088373  lea     r8, [rsp+88h+arg_0]; unsigned int *
0x14008837b  mov     [rsp+88h+arg_0], r15d
0x140088383  mov     edx, 53h ; 'S'; unsigned int
0x140088388  mov     [rsp+88h+arg_10], r15d
0x140088390  mov     rcx, rbp; this
0x140088393  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x140088398  mov     ecx, [rsp+88h+arg_0]
0x14008839f  mov     edx, eax
0x1400883a1  test    eax, eax
0x1400883a3  jnz     loc_140088525
0x1400883a9  cmp     ecx, 8
0x1400883ac  jnz     loc_140088525
0x1400883b2  mov     rax, [rsp+88h+arg_18]
0x1400883ba  mov     rbx, [rax]
0x1400883bd  add     rbx, 0BEBC200h
0x1400883c4  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x1400883c9  cmp     rax, rbx
0x1400883cc  jnb     loc_1400884E6
0x1400883d2  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400883d9  lea     rbx, [rdi+8Ch]
0x1400883e0  jz      short loc_14008840B
0x1400883e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400883e9  mov     r9d, 2Ch ; ','
0x1400883ef  movzx   eax, word ptr [rbx]
0x1400883f2  mov     dl, 4
0x1400883f4  mov     [rsp+88h+var_58], eax
0x1400883f8  mov     [rsp+88h+var_60], rsi
0x1400883fd  mov     rcx, [rcx+40h]
0x140088401  mov     [rsp+88h+var_68], r13
0x140088406  call    WPP_RECORDER_SF_qD
0x14008840b  lea     r8, [rsp+88h+arg_10]; unsigned int *
0x140088413  mov     edx, 54h ; 'T'; unsigned int
0x140088418  mov     rcx, rbp; this
0x14008841b  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x140088420  mov     ecx, eax
0x140088422  test    eax, eax
0x140088424  jnz     short loc_140088437
0x140088426  mov     r9d, [rsp+88h+arg_10]
0x14008842e  cmp     r9d, 0FFFFh
0x140088435  jnz     short loc_14008847A
0x140088437  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14008843e  jz      short loc_140088474
0x140088440  movzx   eax, word ptr [rbx]
0x140088443  mov     r9d, 2Dh ; '-'
0x140088449  mov     dword ptr [rsp+88h+var_50], ecx
0x14008844d  mov     dl, 2
0x14008844f  mov     rcx, cs:WPP_GLOBAL_Control
0x140088456  mov     [rsp+88h+var_58], eax
0x14008845a  mov     [rsp+88h+var_60], rsi
0x14008845f  mov     [rsp+88h+var_68], r13
0x140088464  mov     rcx, [rcx+40h]
0x140088468  call    WPP_RECORDER_SF_qDD
0x14008846d  lea     rbx, [rdi+8Ch]
0x140088474  mov     r9d, 0Ah
0x14008847a  mov     r8d, 3
0x140088480  mov     ecx, r8d
0x140088483  call    ?GetRoamConfig@CConnectHelpers@@YA?AW4_WDI_ROAM_CONFIGURATION_FLAGS@@W4_WFC_ROAM_CONNECT_TRIGGER@@@Z; CConnectHelpers::GetRoamConfig(_WFC_ROAM_CONNECT_TRIGGER)
0x140088488  mov     rcx, rsi
0x14008848b  mov     dword ptr [rsp+88h+var_60], 2
0x140088493  mov     rdx, r14
0x140088496  mov     dword ptr [rsp+88h+var_68], eax
0x14008849a  call    ?StartRoamJob@CPort@@QEAAHPEAPEAVCRoamReconnectJob@@W4_WFC_ROAM_CONNECT_TRIGGER@@W4_WDI_ASSOC_STATUS@@W4_WDI_ROAM_CONFIGURATION_FLAGS@@W4_WDF_EXECUTION_LEVEL@@@Z; CPort::StartRoamJob(CRoamReconnectJob * *,_WFC_ROAM_CONNECT_TRIGGER,_WDI_ASSOC_STATUS,_WDI_ROAM_CONFIGURATION_FLAGS,_WDF_EXECUTION_LEVEL)
0x14008849f  test    eax, eax
0x1400884a1  jz      loc_14008871B
0x1400884a7  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400884ae  jz      loc_140088757
0x1400884b4  movzx   ecx, word ptr [rbx]
0x1400884b7  mov     r9d, 2Eh ; '.'
0x1400884bd  mov     dword ptr [rsp+88h+var_50], eax
0x1400884c1  mov     dl, 2
0x1400884c3  mov     [rsp+88h+var_58], ecx
0x1400884c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400884ce  mov     [rsp+88h+var_60], rsi
0x1400884d3  mov     [rsp+88h+var_68], r13
0x1400884d8  mov     rcx, [rcx+40h]
0x1400884dc  call    WPP_RECORDER_SF_qDD
0x1400884e1  jmp     loc_14008871B
0x1400884e6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400884ed  jz      loc_140088757
0x1400884f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400884fa  mov     r9d, 2Fh ; '/'
0x140088500  movzx   eax, word ptr [rdi+8Ch]
0x140088507  mov     dl, 4
0x140088509  mov     [rsp+88h+var_58], eax
0x14008850d  mov     [rsp+88h+var_60], rsi
0x140088512  mov     rcx, [rcx+40h]
0x140088516  mov     [rsp+88h+var_68], r13
0x14008851b  call    WPP_RECORDER_SF_qD
0x140088520  jmp     loc_14008871B
0x140088525  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14008852c  jz      loc_140088757
0x140088532  movzx   eax, word ptr [rbx]
0x140088535  mov     r9d, 30h ; '0'
0x14008853b  mov     [rsp+88h+var_48], ecx
0x14008853f  mov     rcx, cs:WPP_GLOBAL_Control
0x140088546  mov     dword ptr [rsp+88h+var_50], edx
0x14008854a  mov     dl, 2
0x14008854c  mov     [rsp+88h+var_58], eax
0x140088550  mov     [rsp+88h+var_60], rsi
0x140088555  mov     rcx, [rcx+40h]
0x140088559  mov     [rsp+88h+var_68], r13
0x14008855e  call    WPP_RECORDER_SF_qDdd
0x140088563  jmp     loc_14008871B
0x140088568  cmp     rbx, [rdi+188h]
0x14008856f  jnz     short loc_140088580
0x140088571  mov     edx, ebp; int
0x140088573  mov     rcx, rsi; this
0x140088576  call    ?OnReconnectCompleted@CPort@@AEAAXH@Z; CPort::OnReconnectCompleted(int)
0x14008857b  jmp     loc_14008871B
0x140088580  cmp     rbx, [rsi+198h]
0x140088587  jnz     short loc_1400885EC
0x140088589  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140088590  jz      short loc_1400885C3
0x140088592  mov     rcx, cs:WPP_GLOBAL_Control
0x140088599  mov     r9d, 31h ; '1'
0x14008859f  movzx   eax, word ptr [rdi+8Ch]
0x1400885a6  mov     dl, 4
0x1400885a8  mov     dword ptr [rsp+88h+var_50], ebp
0x1400885ac  mov     [rsp+88h+var_58], eax
0x1400885b0  mov     rcx, [rcx+40h]
0x1400885b4  mov     [rsp+88h+var_60], rsi
0x1400885b9  mov     [rsp+88h+var_68], r13
0x1400885be  call    WPP_RECORDER_SF_qDD
0x1400885c3  mov     rcx, [rdi+190h]
0x1400885ca  test    rcx, rcx
0x1400885cd  jz      short loc_1400885E0
0x1400885cf  mov     rax, [rcx]
0x1400885d2  mov     edx, 1
0x1400885d7  mov     rax, [rax+28h]
0x1400885db  call    _guard_dispatch_icall
0x1400885e0  mov     [rdi+190h], r15
0x1400885e7  jmp     loc_14008871B
0x1400885ec  cmp     rbx, [rdi+1A0h]
0x1400885f3  jnz     short loc_140088658
0x1400885f5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400885fc  jz      short loc_14008862F
0x1400885fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140088605  mov     r9d, 32h ; '2'
0x14008860b  movzx   eax, word ptr [rdi+8Ch]
0x140088612  mov     dl, 4
0x140088614  mov     dword ptr [rsp+88h+var_50], ebp
0x140088618  mov     [rsp+88h+var_58], eax
0x14008861c  mov     rcx, [rcx+40h]
0x140088620  mov     [rsp+88h+var_60], rsi
0x140088625  mov     [rsp+88h+var_68], r13
0x14008862a  call    WPP_RECORDER_SF_qDD
0x14008862f  mov     rcx, [rdi+1A0h]
0x140088636  test    rcx, rcx
0x140088639  jz      short loc_14008864C
0x14008863b  mov     rax, [rcx]
0x14008863e  mov     edx, 1
0x140088643  mov     rax, [rax+28h]
0x140088647  call    _guard_dispatch_icall
0x14008864c  mov     [rdi+1A0h], r15
0x140088653  jmp     loc_14008871B
0x140088658  cmp     rbx, [rdi+198h]
0x14008865f  jnz     short loc_1400886C1
0x140088661  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140088668  jz      short loc_14008869B
0x14008866a  mov     rcx, cs:WPP_GLOBAL_Control
0x140088671  mov     r9d, 33h ; '3'
0x140088677  movzx   eax, word ptr [rdi+8Ch]
0x14008867e  mov     dl, 4
0x140088680  mov     dword ptr [rsp+88h+var_50], ebp
0x140088684  mov     [rsp+88h+var_58], eax
0x140088688  mov     rcx, [rcx+40h]
0x14008868c  mov     [rsp+88h+var_60], rsi
0x140088691  mov     [rsp+88h+var_68], r13
0x140088696  call    WPP_RECORDER_SF_qDD
0x14008869b  mov     rcx, [rdi+198h]
0x1400886a2  test    rcx, rcx
0x1400886a5  jz      short loc_1400886B8
0x1400886a7  mov     rax, [rcx]
0x1400886aa  mov     edx, 1
0x1400886af  mov     rax, [rax+28h]
0x1400886b3  call    _guard_dispatch_icall
0x1400886b8  mov     [rdi+198h], r15
0x1400886bf  jmp     short loc_14008871B
0x1400886c1  test    rbx, rbx
0x1400886c4  jz      short loc_14008871B
0x1400886c6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400886cd  jz      short loc_140088707
0x1400886cf  movzx   ecx, word ptr [rdi+8Ch]
0x1400886d6  mov     r9d, 34h ; '4'
0x1400886dc  mov     eax, [rbx+3Ch]
0x1400886df  mov     dl, 4
0x1400886e1  mov     [rsp+88h+var_48], ebp
0x1400886e5  mov     dword ptr [rsp+88h+var_50], eax
0x1400886e9  mov     [rsp+88h+var_58], ecx
0x1400886ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400886f4  mov     [rsp+88h+var_60], rsi
0x1400886f9  mov     [rsp+88h+var_68], r13
0x1400886fe  mov     rcx, [rcx+40h]
0x140088702  call    WPP_RECORDER_SF_qDdd
0x140088707  mov     rax, [rbx]
0x14008870a  mov     edx, 1
0x14008870f  mov     rcx, rbx
0x140088712  mov     rax, [rax+28h]
0x140088716  call    _guard_dispatch_icall
0x14008871b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140088722  jz      short loc_140088757
0x140088724  mov     rcx, cs:WPP_GLOBAL_Control
0x14008872b  cmp     byte ptr [rcx+29h], 5
0x14008872f  jnb     short loc_140088738
0x140088731  cmp     [rcx+48h], r15w
0x140088736  jz      short loc_140088757
0x140088738  mov     rcx, [rcx+40h]
0x14008873c  mov     r9d, 35h ; '5'
0x140088742  mov     dword ptr [rsp+88h+var_60], r15d
0x140088747  mov     dl, 5
0x140088749  mov     [rsp+88h+var_68], r13
0x14008874e  lea     r8d, [r9-34h]
0x140088752  call    WPP_RECORDER_SF_d
0x140088757  mov     rbx, [rsp+88h+arg_8]
0x14008875f  add     rsp, 50h
0x140088763  pop     r15
0x140088765  pop     r14
0x140088767  pop     r13
0x140088769  pop     r12
0x14008876b  pop     rdi
0x14008876c  pop     rsi
0x14008876d  pop     rbp
0x14008876e  retn
```
