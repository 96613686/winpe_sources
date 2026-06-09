# BthServRemoveSdpRecords(void *)

- ea: `0x180015df8`
- end: `0x1800160d0`
- name: `?BthServRemoveSdpRecords@@YAXPEAX@Z`
- size: `728`
- prototype: `void __fastcall(char *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180011dec`

## callees

- `0x18000d404`
- `0x18000f2e8`
- `0x1800110d0`
- `0x1800110fc`
- `0x180011194`
- `0x18001140c`
- `0x180012e00`
- `0x180015db4`
- `0x180015df8`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180016070`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180016070`

## pseudocode

```c
void __fastcall BthServRemoveSdpRecords(char *a1)
{
  char v2; // di
  bool v3; // dl
  _QWORD *v4; // rcx
  bool v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 *v8; // rsi
  _QWORD **v9; // rbx
  _QWORD *v10; // rax
  _QWORD *v11; // rcx
  _QWORD *v12; // r14
  __int64 v13; // rcx
  volatile signed __int32 *v14; // rbx
  int v15; // [rsp+20h] [rbp-88h]
  DWORD v16; // [rsp+28h] [rbp-80h]
  __int64 *v17; // [rsp+60h] [rbp-48h] BYREF
  volatile signed __int32 *v18; // [rsp+68h] [rbp-40h]
  DWORD NumberOfBytesTransferred; // [rsp+B0h] [rbp+8h] BYREF

  NumberOfBytesTransferred = 0;
  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  if ( (unsigned int)BthServLockDbClients() )
  {
    BthServGlobals::GetSafeRadioHandle(&Globals, &v17);
    v8 = v17;
    if ( v17 && (unsigned __int64)(*v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v9 = (_QWORD **)(a1 + 56);
      while ( 1 )
      {
        v10 = *v9;
        if ( *v9 == v9 )
          break;
        if ( (_QWORD **)v10[1] != v9 || (v11 = (_QWORD *)*v10, *(_QWORD **)(*v10 + 8LL) != v10) )
          __fastfail(3u);
        *v9 = v11;
        v12 = v10 - 1;
        v11[1] = v9;
        LOBYTE(v6) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
        if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sqi(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v6,
            v7,
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v15,
            v16,
            20,
            (__int64)WPP_db4ee0e4eaba3bdc4454fe810b066fe8_Traceguids);
        }
        if ( v8 )
          v13 = *v8;
        else
          v13 = -1;
        BthServOverlappedIoctl((HANDLE)v13, 0x410218u, v12, 8u, 0, 0, &NumberOfBytesTransferred);
        SdpFreePool(v12);
      }
    }
    else
    {
      LOBYTE(v6) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v6,
          v7,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v15,
          v16,
          21,
          (__int64)WPP_db4ee0e4eaba3bdc4454fe810b066fe8_Traceguids);
    }
    v14 = v18;
    if ( v18 )
    {
      if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *, __int64, __int64))v14)(v14, v6, v7);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
    ReleaseMutex(qword_180044B50);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      v2 = 0;
    v5 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_49;
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      v2 = 0;
    v5 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
LABEL_49:
      WPP_RECORDER_AND_TRACE_SF_s(v4[2], v2, v5, v4[5]);
  }
}

```

## disassembly

```asm
0x180015df8  mov     rax, rsp
0x180015dfb  push    rbx
0x180015dfc  push    rbp
0x180015dfd  push    rsi
0x180015dfe  push    rdi
0x180015dff  push    r13
0x180015e01  push    r14
0x180015e03  sub     rsp, 78h
0x180015e07  mov     rbp, rcx
0x180015e0a  mov     dword ptr [rax+8], 0
0x180015e11  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e18  lea     r13, WPP_GLOBAL_Control
0x180015e1f  mov     edi, 1
0x180015e24  cmp     rcx, r13
0x180015e27  jz      short loc_180015E34
0x180015e29  cmp     byte ptr [rcx+19h], 4
0x180015e2d  jb      short loc_180015E34
0x180015e2f  mov     dl, dil
0x180015e32  jmp     short loc_180015E36
0x180015e34  xor     dl, dl
0x180015e36  lea     r14, WPP_RECORDER_INITIALIZED
0x180015e3d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180015e44  lea     rbx, WPP_db4ee0e4eaba3bdc4454fe810b066fe8_Traceguids
0x180015e4b  setnz   r8b
0x180015e4f  test    dl, dl
0x180015e51  jnz     short loc_180015E58
0x180015e53  test    r8b, r8b
0x180015e56  jz      short loc_180015E76
0x180015e58  mov     r9, [rcx+28h]
0x180015e5c  mov     rcx, [rcx+10h]
0x180015e60  mov     [rsp+0A8h+var_60], rbp
0x180015e65  mov     [rsp+0A8h+var_70], rbx
0x180015e6a  mov     word ptr [rsp+0A8h+lpNumberOfBytesTransferred], 12h
0x180015e71  call    WPP_RECORDER_AND_TRACE_SF_si
0x180015e76  call    ?BthServLockDbClients@@YAHXZ; BthServLockDbClients(void)
0x180015e7b  test    eax, eax
0x180015e7d  jnz     short loc_180015EBE
0x180015e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e86  cmp     rcx, r13
0x180015e89  jz      short loc_180015E91
0x180015e8b  cmp     byte ptr [rcx+19h], 4
0x180015e8f  jnb     short loc_180015E94
0x180015e91  xor     dil, dil
0x180015e94  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180015e9b  setnz   r8b
0x180015e9f  test    dil, dil
0x180015ea2  jnz     short loc_180015EAD
0x180015ea4  test    r8b, r8b
0x180015ea7  jz      loc_1800160C3
0x180015ead  mov     [rsp+0A8h+var_70], rbx
0x180015eb2  mov     word ptr [rsp+0A8h+lpNumberOfBytesTransferred], 13h
0x180015eb9  jmp     loc_1800160B3
0x180015ebe  lea     rdx, [rsp+0A8h+var_48]
0x180015ec3  lea     rcx, ?Globals@@3VBthServGlobals@@A; BthServGlobals Globals
0x180015eca  call    ?GetSafeRadioHandle@BthServGlobals@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; BthServGlobals::GetSafeRadioHandle(void)
0x180015ecf  mov     rsi, [rsp+0A8h+var_48]
0x180015ed4  test    rsi, rsi
0x180015ed7  jz      loc_180015FD3
0x180015edd  mov     rax, [rsi]
0x180015ee0  sub     rax, rdi
0x180015ee3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180015ee7  ja      loc_180015FD3
0x180015eed  lea     rbx, [rbp+38h]
0x180015ef1  mov     rax, [rbx]
0x180015ef4  cmp     rax, rbx
0x180015ef7  jz      loc_180016023
0x180015efd  cmp     [rax+8], rbx
0x180015f01  jnz     loc_180015FCC
0x180015f07  mov     rcx, [rax]
0x180015f0a  cmp     [rcx+8], rax
0x180015f0e  jnz     loc_180015FCC
0x180015f14  mov     [rbx], rcx
0x180015f17  lea     r14, [rax-8]
0x180015f1b  mov     [rcx+8], rbx
0x180015f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f26  cmp     rcx, r13
0x180015f29  jz      short loc_180015F36
0x180015f2b  cmp     byte ptr [rcx+19h], 4
0x180015f2f  jb      short loc_180015F36
0x180015f31  mov     dl, dil
0x180015f34  jmp     short loc_180015F38
0x180015f36  xor     dl, dl
0x180015f38  lea     rax, WPP_RECORDER_INITIALIZED
0x180015f3f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180015f46  setnz   r8b
0x180015f4a  test    dl, dl
0x180015f4c  jnz     short loc_180015F53
0x180015f4e  test    r8b, r8b
0x180015f51  jz      short loc_180015F80
0x180015f53  mov     rax, [r14]
0x180015f56  mov     r9, [rcx+28h]
0x180015f5a  mov     rcx, [rcx+10h]
0x180015f5e  mov     [rsp+0A8h+var_58], rbp
0x180015f63  mov     [rsp+0A8h+var_60], rax
0x180015f68  lea     rax, WPP_db4ee0e4eaba3bdc4454fe810b066fe8_Traceguids
0x180015f6f  mov     [rsp+0A8h+var_70], rax
0x180015f74  mov     word ptr [rsp+0A8h+lpNumberOfBytesTransferred], 14h
0x180015f7b  call    WPP_RECORDER_AND_TRACE_SF_sqi
0x180015f80  test    rsi, rsi
0x180015f83  jz      short loc_180015F8A
0x180015f85  mov     rcx, [rsi]
0x180015f88  jmp     short loc_180015F8E
0x180015f8a  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180015f8e  lea     rax, [rsp+0A8h+NumberOfBytesTransferred]
0x180015f96  mov     r9d, 8; nInBufferSize
0x180015f9c  mov     [rsp+0A8h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180015fa1  mov     r8, r14; lpInBuffer
0x180015fa4  mov     [rsp+0A8h+var_80], 0; DWORD
0x180015fac  mov     edx, 410218h; dwIoControlCode
0x180015fb1  mov     [rsp+0A8h+var_88], 0; void *
0x180015fba  call    ?BthServOverlappedIoctl@@YAKPEAXK0K0KPEAK@Z; BthServOverlappedIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x180015fbf  mov     rcx, r14
0x180015fc2  call    SdpFreePool
0x180015fc7  jmp     loc_180015EF1
0x180015fcc  mov     ecx, 3
0x180015fd1  int     29h; Win8: RtlFailFast(ecx)
0x180015fd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180015fda  cmp     rcx, r13
0x180015fdd  jz      short loc_180015FEA
0x180015fdf  cmp     byte ptr [rcx+19h], 3
0x180015fe3  jb      short loc_180015FEA
0x180015fe5  mov     dl, dil
0x180015fe8  jmp     short loc_180015FEC
0x180015fea  xor     dl, dl
0x180015fec  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180015ff3  setnz   r8b
0x180015ff7  test    dl, dl
0x180015ff9  jnz     short loc_180016000
0x180015ffb  test    r8b, r8b
0x180015ffe  jz      short loc_18001602A
0x180016000  mov     r9, [rcx+28h]
0x180016004  mov     rcx, [rcx+10h]
0x180016008  mov     dword ptr [rsp+0A8h+var_60], 80070006h
0x180016010  mov     [rsp+0A8h+var_70], rbx
0x180016015  mov     word ptr [rsp+0A8h+lpNumberOfBytesTransferred], 15h
0x18001601c  call    WPP_RECORDER_AND_TRACE_SF_sd
0x180016021  jmp     short loc_18001602A
0x180016023  lea     r14, WPP_RECORDER_INITIALIZED
0x18001602a  mov     rbx, [rsp+0A8h+var_40]
0x18001602f  test    rbx, rbx
0x180016032  jz      short loc_180016069
0x180016034  or      eax, 0FFFFFFFFh
0x180016037  lock xadd [rbx+8], eax
0x18001603c  cmp     eax, edi
0x18001603e  jnz     short loc_180016069
0x180016040  mov     rax, [rbx]
0x180016043  mov     rcx, rbx
0x180016046  mov     rax, [rax]
0x180016049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001604e  or      eax, 0FFFFFFFFh
0x180016051  lock xadd [rbx+0Ch], eax
0x180016056  cmp     eax, edi
0x180016058  jnz     short loc_180016069
0x18001605a  mov     rax, [rbx]
0x18001605d  mov     rcx, rbx
0x180016060  mov     rax, [rax+8]
0x180016064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016069  mov     rcx, cs:qword_180044B50; hMutex
0x180016070  call    cs:__imp_ReleaseMutex
0x180016076  mov     rcx, cs:WPP_GLOBAL_Control
0x18001607d  cmp     rcx, r13
0x180016080  jz      short loc_180016088
0x180016082  cmp     byte ptr [rcx+19h], 4
0x180016086  jnb     short loc_18001608B
0x180016088  xor     dil, dil
0x18001608b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180016092  setnz   r8b
0x180016096  test    dil, dil
0x180016099  jnz     short loc_1800160A0
0x18001609b  test    r8b, r8b
0x18001609e  jz      short loc_1800160C3
0x1800160a0  lea     rdx, WPP_db4ee0e4eaba3bdc4454fe810b066fe8_Traceguids
0x1800160a7  mov     [rsp+0A8h+var_70], rdx
0x1800160ac  mov     word ptr [rsp+0A8h+lpNumberOfBytesTransferred], 16h
0x1800160b3  mov     r9, [rcx+28h]
0x1800160b7  mov     dl, dil
0x1800160ba  mov     rcx, [rcx+10h]
0x1800160be  call    WPP_RECORDER_AND_TRACE_SF_s
0x1800160c3  add     rsp, 78h
0x1800160c7  pop     r14
0x1800160c9  pop     r13
0x1800160cb  pop     rdi
0x1800160cc  pop     rsi
0x1800160cd  pop     rbp
0x1800160ce  pop     rbx
0x1800160cf  retn
```
