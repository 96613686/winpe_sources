# WxDevice::CompleteWdfPowerManagedJob(_WX_WDF_POWER_MANAGED_JOB_REQUEST_CONTEXT * const,long)

- ea: `0x1400183f4`
- end: `0x1400185ef`
- name: `?CompleteWdfPowerManagedJob@WxDevice@@QEAAXQEAU_WX_WDF_POWER_MANAGED_JOB_REQUEST_CONTEXT@@J@Z`
- size: `507`
- prototype: `void __fastcall(WxDevice *__hidden this, struct _WX_WDF_POWER_MANAGED_JOB_REQUEST_CONTEXT *const, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140004d90`

## callees

- `0x140009420`
- `0x14000c778`
- `0x14000c940`
- `0x1400156d0`
- `0x1400183f4`
- `0x140018c14`
- `0x14001eed0`
- `0x1400cf130`
- `0x1400dfd40`

## import_xrefs

- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x140018448`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x140018448`

## pseudocode

```c
void __fastcall WxDevice::CompleteWdfPowerManagedJob(
        WxDevice *this,
        struct _WX_WDF_POWER_MANAGED_JOB_REQUEST_CONTEXT *const a2,
        unsigned int a3)
{
  __int64 v3; // rdi
  Event *v7; // rbx
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  int v11; // r13d
  int v12; // ebp
  __int64 v13; // r12
  Event *v14; // rax
  char v15; // si
  int v16; // edi
  EventQueue *v17; // rcx
  int v18; // [rsp+20h] [rbp-68h]
  __int64 v19; // [rsp+28h] [rbp-60h]
  int v20; // [rsp+A0h] [rbp+18h]

  v3 = *(_QWORD *)a2;
  v7 = (Event *)(*(_QWORD *)a2 + 208LL);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)a2 + 32LL))(*(_QWORD *)a2);
  v11 = *(_DWORD *)(v3 + 16);
  v20 = *(_DWORD *)(v3 + 60);
  if ( a3 == -1073741536 )
    v12 = -1073676276;
  else
    v12 = NdisConvertNtStatusToNdisStatus(a3);
  v13 = *((_QWORD *)a2 + 1);
  if ( v7 )
  {
    v15 = 0;
  }
  else
  {
    v14 = (Event *)operator new(0x48u);
    if ( !v14 || (v7 = Event::Event(v14, 0, 0)) == 0 )
    {
      v16 = -1073741670;
LABEL_22:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v19) = v16;
        LOBYTE(v8) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          1,
          100,
          (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
          v19);
      }
      return;
    }
    v15 = 1;
  }
  v17 = (WxDevice *)((char *)this + 792);
  if ( this == (WxDevice *)-792LL )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        v9,
        10,
        (__int64)WPP_36ec87e851083ecb6deb1777feb2ecc6_Traceguids,
        (char)v7,
        *(_DWORD *)v7);
    }
    v16 = -1073741811;
  }
  else if ( *((_BYTE *)v7 + 45) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        v9,
        11,
        (__int64)WPP_36ec87e851083ecb6deb1777feb2ecc6_Traceguids,
        (char)v7,
        *(_DWORD *)v7);
    }
    v16 = -1073741436;
  }
  else
  {
    *((_DWORD *)v7 + 4) = 1;
    *((_QWORD *)v7 + 1) = v17;
    *((_QWORD *)v7 + 4) = v13;
    *((_QWORD *)v7 + 3) = v3;
    *((_DWORD *)v7 + 10) = v12;
    v16 = EventQueue::QueueEvent(v17, v7, 0);
  }
  if ( v16 )
  {
    if ( v15 )
      operator delete(v7);
    goto LABEL_22;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_DLd(WPP_GLOBAL_Control->DeviceExtension, v8, v9, v10, v18, v11, v20, a3);
}

```

## disassembly

```asm
0x1400183f4  push    rbx
0x1400183f6  push    rbp
0x1400183f7  push    rsi
0x1400183f8  push    rdi
0x1400183f9  push    r12
0x1400183fb  push    r13
0x1400183fd  push    r14
0x1400183ff  push    r15
0x140018401  sub     rsp, 48h
0x140018405  mov     rdi, [rdx]
0x140018408  mov     r14d, r8d
0x14001840b  mov     rsi, rdx
0x14001840e  mov     r15, rcx
0x140018411  lea     rbx, [rdi+0D0h]
0x140018418  mov     rax, [rdi]
0x14001841b  mov     rcx, rdi
0x14001841e  mov     rax, [rax+20h]
0x140018422  call    _guard_dispatch_icall
0x140018427  mov     eax, [rdi+3Ch]
0x14001842a  mov     r13d, [rdi+10h]
0x14001842e  mov     [rsp+88h+arg_10], eax
0x140018435  cmp     r14d, 0C0000120h
0x14001843c  jnz     short loc_140018445
0x14001843e  mov     ebp, 0C001000Ch
0x140018443  jmp     short loc_140018456
0x140018445  mov     ecx, r14d
0x140018448  call    cs:__imp_NdisConvertNtStatusToNdisStatus
0x14001844f  nop     dword ptr [rax+rax+00h]
0x140018454  mov     ebp, eax
0x140018456  mov     r12, [rsi+8]
0x14001845a  lea     rax, WPP_RECORDER_INITIALIZED
0x140018461  test    rbx, rbx
0x140018464  jnz     short loc_14001849E
0x140018466  lea     ecx, [rbx+48h]; unsigned __int64
0x140018469  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001846e  test    rax, rax
0x140018471  jz      short loc_140018494
0x140018473  xor     r8d, r8d; unsigned int
0x140018476  xor     edx, edx; bool
0x140018478  mov     rcx, rax; this
0x14001847b  call    ??0Event@@QEAA@_NK@Z; Event::Event(bool,ulong)
0x140018480  mov     rbx, rax
0x140018483  test    rax, rax
0x140018486  jz      short loc_140018494
0x140018488  mov     sil, 1
0x14001848b  lea     rax, WPP_RECORDER_INITIALIZED
0x140018492  jmp     short loc_1400184A1
0x140018494  mov     edi, 0C000009Ah
0x140018499  jmp     loc_14001856A
0x14001849e  xor     sil, sil
0x1400184a1  lea     rcx, [r15+318h]; this
0x1400184a8  test    rcx, rcx
0x1400184ab  jz      short loc_140018517
0x1400184ad  cmp     byte ptr [rbx+2Dh], 0
0x1400184b1  jz      short loc_1400184F2
0x1400184b3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400184ba  jz      short loc_1400184EB
0x1400184bc  mov     eax, [rbx]
0x1400184be  mov     r9d, 0Bh
0x1400184c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400184cb  mov     dl, 2
0x1400184cd  mov     [rsp+88h+var_58], eax
0x1400184d1  lea     rax, WPP_36ec87e851083ecb6deb1777feb2ecc6_Traceguids
0x1400184d8  mov     [rsp+88h+var_60], rbx
0x1400184dd  mov     [rsp+88h+var_68], rax
0x1400184e2  mov     rcx, [rcx+40h]
0x1400184e6  call    WPP_RECORDER_SF_qD
0x1400184eb  mov     edi, 0C0000184h
0x1400184f0  jmp     short loc_140018554
0x1400184f2  xor     r8d, r8d; bool
0x1400184f5  mov     dword ptr [rbx+10h], 1
0x1400184fc  mov     rdx, rbx; struct Event *
0x1400184ff  mov     [rbx+8], rcx
0x140018503  mov     [rbx+20h], r12
0x140018507  mov     [rbx+18h], rdi
0x14001850b  mov     [rbx+28h], ebp
0x14001850e  call    ?QueueEvent@EventQueue@@QEAAHPEAVEvent@@_N@Z; EventQueue::QueueEvent(Event *,bool)
0x140018513  mov     edi, eax
0x140018515  jmp     short loc_140018554
0x140018517  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001851e  jz      short loc_14001854F
0x140018520  mov     eax, [rbx]
0x140018522  mov     r9d, 0Ah
0x140018528  mov     rcx, cs:WPP_GLOBAL_Control
0x14001852f  mov     dl, 2
0x140018531  mov     [rsp+88h+var_58], eax
0x140018535  lea     rax, WPP_36ec87e851083ecb6deb1777feb2ecc6_Traceguids
0x14001853c  mov     [rsp+88h+var_60], rbx
0x140018541  mov     [rsp+88h+var_68], rax
0x140018546  mov     rcx, [rcx+40h]
0x14001854a  call    WPP_RECORDER_SF_qD
0x14001854f  mov     edi, 0C000000Dh
0x140018554  test    edi, edi
0x140018556  jz      short loc_1400185A8
0x140018558  test    rbx, rbx
0x14001855b  jz      short loc_14001856A
0x14001855d  test    sil, sil
0x140018560  jz      short loc_14001856A
0x140018562  mov     rcx, rbx; void *
0x140018565  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001856a  lea     rax, WPP_RECORDER_INITIALIZED
0x140018571  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018578  jz      short loc_1400185DD
0x14001857a  mov     rcx, cs:WPP_GLOBAL_Control
0x140018581  lea     rax, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x140018588  mov     r9d, 64h ; 'd'
0x14001858e  mov     dword ptr [rsp+88h+var_60], edi
0x140018592  mov     dl, 2
0x140018594  mov     [rsp+88h+var_68], rax
0x140018599  mov     rcx, [rcx+40h]
0x14001859d  lea     r8d, [r9-63h]
0x1400185a1  call    WPP_RECORDER_SF_d
0x1400185a6  jmp     short loc_1400185DD
0x1400185a8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400185af  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400185b6  jz      short loc_1400185DD
0x1400185b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400185bf  mov     eax, [rsp+88h+arg_10]
0x1400185c6  mov     [rsp+88h+var_50], r14d
0x1400185cb  mov     [rsp+88h+var_58], eax
0x1400185cf  mov     rcx, [rcx+40h]
0x1400185d3  mov     dword ptr [rsp+88h+var_60], r13d
0x1400185d8  call    WPP_RECORDER_SF_DLd
0x1400185dd  add     rsp, 48h
0x1400185e1  pop     r15
0x1400185e3  pop     r14
0x1400185e5  pop     r13
0x1400185e7  pop     r12
0x1400185e9  pop     rdi
0x1400185ea  pop     rsi
0x1400185eb  pop     rbp
0x1400185ec  pop     rbx
0x1400185ed  retn
```
