# CDeviceInitializeJob::OnJobStepCompleted(int,void *)

- ea: `0x14006a230`
- end: `0x14006a528`
- name: `?OnJobStepCompleted@CDeviceInitializeJob@@UEAAXHPEAX@Z`
- size: `760`
- prototype: `void __fastcall(CDeviceInitializeJob *__hidden this, int, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x14000c940`
- `0x14000d054`
- `0x140017130`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002bd34`
- `0x140068e44`
- `0x14006a230`
- `0x14006b410`
- `0x1400dfd40`

## pseudocode

```c
void __fastcall CDeviceInitializeJob::OnJobStepCompleted(CDeviceInitializeJob *this, __int64 a2, void *a3)
{
  unsigned int v3; // ebp
  char v4; // si
  int PropertyBoolean; // edi
  _QWORD *v7; // rcx
  CPropertyCache *v8; // rax
  int v9; // r9d
  CPropertyCache *v10; // rax
  unsigned __int8 v11; // si
  __int64 v12; // [rsp+38h] [rbp-40h]
  unsigned __int8 v13; // [rsp+80h] [rbp+8h] BYREF
  unsigned __int8 v14; // [rsp+88h] [rbp+10h] BYREF

  v3 = *((_DWORD *)this + 134);
  v4 = 0;
  v13 = 0;
  v14 = 0;
  PropertyBoolean = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      45,
      (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  if ( *((_DWORD *)this + 134) == 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        20,
        (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        PropertyBoolean);
    }
    v7 = (_QWORD *)*((_QWORD *)this + 159);
    if ( v7 )
    {
      operator delete(v7);
      *((_QWORD *)this + 159) = 0;
    }
    v3 = 2;
    v8 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)(*((_QWORD *)this + 68) + 8LL)
                                                                               + 8LL))(
                             *((_QWORD *)this + 68) + 8LL,
                             a2,
                             a3);
    PropertyBoolean = CPropertyCache::GetPropertyBoolean(v8, 0x2Fu, &v14);
    if ( PropertyBoolean )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v9 = 46;
LABEL_27:
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          (_DWORD)a3,
          v9,
          (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
      }
    }
    else
    {
      v10 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 68) + 8LL) + 8LL))(*((_QWORD *)this + 68) + 8LL);
      PropertyBoolean = CPropertyCache::GetPropertyBoolean(v10, 0x75u, &v13);
      if ( !PropertyBoolean )
      {
        v11 = v13;
        if ( v14 != v13 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(a2) = 4;
            WPP_RECORDER_SF_qDdd(
              WPP_GLOBAL_Control->DeviceExtension,
              a2,
              (_DWORD)a3,
              48,
              (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids,
              (char)this,
              *((_DWORD *)this + 4),
              v13,
              v14);
          }
          PropertyBoolean = CDeviceInitializeJob::StartSetRadioStateTask(this, v11);
          if ( !PropertyBoolean )
          {
            *((_DWORD *)this + 134) = 2;
            goto LABEL_15;
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(a2) = 2;
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              a2,
              1,
              49,
              (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids);
          }
          goto LABEL_14;
        }
        goto LABEL_11;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v9 = 47;
        goto LABEL_27;
      }
    }
LABEL_14:
    CDeviceInitializeJob::FinishJob((CAdapter **)this, v3, PropertyBoolean);
    goto LABEL_15;
  }
  if ( *((_DWORD *)this + 134) == 2 )
  {
    if ( PropertyBoolean )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          (_DWORD)a3,
          50,
          (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          PropertyBoolean);
      }
      PropertyBoolean = 0;
    }
LABEL_11:
    *((_DWORD *)this + 134) = 3;
    v4 = 1;
  }
  if ( PropertyBoolean || v4 == 1 )
    goto LABEL_14;
LABEL_15:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    LODWORD(v12) = PropertyBoolean;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      51,
      (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v12);
  }
}

```

## disassembly

```asm
0x14006a230  mov     rax, rsp
0x14006a233  mov     [rax+18h], rbx
0x14006a237  mov     [rax+20h], rbp
0x14006a23b  push    rsi
0x14006a23c  push    rdi
0x14006a23d  push    r12
0x14006a23f  push    r14
0x14006a241  push    r15
0x14006a243  sub     rsp, 50h
0x14006a247  mov     ebp, [rcx+218h]
0x14006a24d  xor     r14d, r14d
0x14006a250  mov     sil, r14b
0x14006a253  mov     [rax+8], r14b
0x14006a257  mov     [rax+10h], r14b
0x14006a25b  mov     edi, edx
0x14006a25d  mov     rbx, rcx
0x14006a260  lea     r15, WPP_RECORDER_INITIALIZED
0x14006a267  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006a26e  lea     r12, WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids
0x14006a275  jz      short loc_14006A2AD
0x14006a277  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a27e  cmp     byte ptr [rcx+29h], 5
0x14006a282  jnb     short loc_14006A28B
0x14006a284  cmp     [rcx+48h], r14w
0x14006a289  jz      short loc_14006A2AD
0x14006a28b  mov     eax, [rbx+10h]
0x14006a28e  mov     r9d, 2Dh ; '-'
0x14006a294  mov     rcx, [rcx+40h]
0x14006a298  mov     dl, 5
0x14006a29a  mov     [rsp+78h+var_48], eax
0x14006a29e  mov     [rsp+78h+var_50], rbx
0x14006a2a3  mov     [rsp+78h+var_58], r12
0x14006a2a8  call    WPP_RECORDER_SF_qD
0x14006a2ad  mov     ecx, [rbx+218h]
0x14006a2b3  sub     ecx, 1
0x14006a2b6  jz      loc_14006A37D
0x14006a2bc  cmp     ecx, 1
0x14006a2bf  jnz     short loc_14006A309
0x14006a2c1  test    edi, edi
0x14006a2c3  jz      short loc_14006A2FC
0x14006a2c5  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006a2cc  jz      short loc_14006A2F9
0x14006a2ce  mov     eax, [rbx+10h]
0x14006a2d1  lea     r9d, [rcx+31h]
0x14006a2d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a2dc  mov     dl, 2
0x14006a2de  mov     dword ptr [rsp+78h+var_40], edi
0x14006a2e2  mov     [rsp+78h+var_48], eax
0x14006a2e6  mov     [rsp+78h+var_50], rbx
0x14006a2eb  mov     rcx, [rcx+40h]
0x14006a2ef  mov     [rsp+78h+var_58], r12
0x14006a2f4  call    WPP_RECORDER_SF_qDD
0x14006a2f9  mov     edi, r14d
0x14006a2fc  mov     dword ptr [rbx+218h], 3
0x14006a306  mov     sil, 1
0x14006a309  test    edi, edi
0x14006a30b  jnz     short loc_14006A313
0x14006a30d  cmp     sil, 1
0x14006a311  jnz     short loc_14006A320
0x14006a313  mov     r8d, edi
0x14006a316  mov     edx, ebp
0x14006a318  mov     rcx, rbx
0x14006a31b  call    ?FinishJob@CDeviceInitializeJob@@AEAAXW4_DEVICE_INITIALIZE_JOB_STATE@@H@Z; CDeviceInitializeJob::FinishJob(_DEVICE_INITIALIZE_JOB_STATE,int)
0x14006a320  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006a327  jz      short loc_14006A363
0x14006a329  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a330  cmp     byte ptr [rcx+29h], 5
0x14006a334  jnb     short loc_14006A33D
0x14006a336  cmp     [rcx+48h], r14w
0x14006a33b  jz      short loc_14006A363
0x14006a33d  mov     eax, [rbx+10h]
0x14006a340  mov     r9d, 33h ; '3'
0x14006a346  mov     rcx, [rcx+40h]
0x14006a34a  mov     dl, 5
0x14006a34c  mov     dword ptr [rsp+78h+var_40], edi
0x14006a350  mov     [rsp+78h+var_48], eax
0x14006a354  mov     [rsp+78h+var_50], rbx
0x14006a359  mov     [rsp+78h+var_58], r12
0x14006a35e  call    WPP_RECORDER_SF_qDD
0x14006a363  lea     r11, [rsp+78h+var_28]
0x14006a368  mov     rbx, [r11+40h]
0x14006a36c  mov     rbp, [r11+48h]
0x14006a370  mov     rsp, r11
0x14006a373  pop     r15
0x14006a375  pop     r14
0x14006a377  pop     r12
0x14006a379  pop     rdi
0x14006a37a  pop     rsi
0x14006a37b  retn
0x14006a37d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006a384  jz      short loc_14006A3B3
0x14006a386  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a38d  mov     r9d, 14h
0x14006a393  mov     eax, [rbx+10h]
0x14006a396  mov     dl, 4
0x14006a398  mov     dword ptr [rsp+78h+var_40], edi
0x14006a39c  mov     [rsp+78h+var_48], eax
0x14006a3a0  mov     rcx, [rcx+40h]
0x14006a3a4  mov     [rsp+78h+var_50], rbx
0x14006a3a9  mov     [rsp+78h+var_58], r12
0x14006a3ae  call    WPP_RECORDER_SF_qDD
0x14006a3b3  mov     rcx, [rbx+4F8h]; void *
0x14006a3ba  test    rcx, rcx
0x14006a3bd  jz      short loc_14006A3CB
0x14006a3bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14006a3c4  mov     [rbx+4F8h], r14
0x14006a3cb  mov     rcx, [rbx+220h]
0x14006a3d2  mov     ebp, 2
0x14006a3d7  add     rcx, 8
0x14006a3db  mov     rax, [rcx]
0x14006a3de  mov     rax, [rax+8]
0x14006a3e2  call    _guard_dispatch_icall
0x14006a3e7  lea     esi, [rbp+2Dh]
0x14006a3ea  mov     rcx, rax; this
0x14006a3ed  mov     edx, esi; unsigned int
0x14006a3ef  lea     r8, [rsp+78h+arg_8]; unsigned __int8 *
0x14006a3f7  call    ?GetPropertyBoolean@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyBoolean(ulong,uchar *)
0x14006a3fc  mov     edi, eax
0x14006a3fe  test    eax, eax
0x14006a400  jz      short loc_14006A43C
0x14006a402  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006a409  jz      loc_14006A313
0x14006a40f  lea     r9d, [rbp+2Ch]
0x14006a413  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a41a  mov     dl, bpl
0x14006a41d  mov     eax, [rbx+10h]
0x14006a420  mov     [rsp+78h+var_48], eax
0x14006a424  mov     [rsp+78h+var_50], rbx
0x14006a429  mov     rcx, [rcx+40h]
0x14006a42d  mov     [rsp+78h+var_58], r12
0x14006a432  call    WPP_RECORDER_SF_qD
0x14006a437  jmp     loc_14006A313
0x14006a43c  mov     rcx, [rbx+220h]
0x14006a443  add     rcx, 8
0x14006a447  mov     rax, [rcx]
0x14006a44a  mov     rax, [rax+8]
0x14006a44e  call    _guard_dispatch_icall
0x14006a453  lea     r8, [rsp+78h+arg_0]; unsigned __int8 *
0x14006a45b  mov     edx, 75h ; 'u'; unsigned int
0x14006a460  mov     rcx, rax; this
0x14006a463  call    ?GetPropertyBoolean@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyBoolean(ulong,uchar *)
0x14006a468  mov     edi, eax
0x14006a46a  test    eax, eax
0x14006a46c  jz      short loc_14006A480
0x14006a46e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006a475  jz      loc_14006A313
0x14006a47b  mov     r9d, esi
0x14006a47e  jmp     short loc_14006A413
0x14006a480  movzx   esi, [rsp+78h+arg_0]
0x14006a488  cmp     [rsp+78h+arg_8], sil
0x14006a490  jz      loc_14006A2FC
0x14006a496  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006a49d  jz      short loc_14006A4D8
0x14006a49f  movzx   eax, [rsp+78h+arg_8]
0x14006a4a7  mov     r9d, 30h ; '0'
0x14006a4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a4b4  mov     dl, 4
0x14006a4b6  mov     [rsp+78h+var_38], eax
0x14006a4ba  mov     eax, [rbx+10h]
0x14006a4bd  mov     dword ptr [rsp+78h+var_40], esi
0x14006a4c1  mov     rcx, [rcx+40h]
0x14006a4c5  mov     [rsp+78h+var_48], eax
0x14006a4c9  mov     [rsp+78h+var_50], rbx
0x14006a4ce  mov     [rsp+78h+var_58], r12
0x14006a4d3  call    WPP_RECORDER_SF_qDdd
0x14006a4d8  mov     dl, sil; unsigned __int8
0x14006a4db  mov     rcx, rbx; this
0x14006a4de  call    ?StartSetRadioStateTask@CDeviceInitializeJob@@AEAAHE@Z; CDeviceInitializeJob::StartSetRadioStateTask(uchar)
0x14006a4e3  mov     edi, eax
0x14006a4e5  test    eax, eax
0x14006a4e7  jz      short loc_14006A51D
0x14006a4e9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006a4f0  jz      loc_14006A313
0x14006a4f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a4fd  mov     r9d, 31h ; '1'
0x14006a503  mov     dl, bpl
0x14006a506  mov     [rsp+78h+var_58], r12
0x14006a50b  mov     rcx, [rcx+40h]
0x14006a50f  lea     r8d, [r9-30h]
0x14006a513  call    WPP_RECORDER_SF_
0x14006a518  jmp     loc_14006A313
0x14006a51d  mov     [rbx+218h], ebp
0x14006a523  jmp     loc_14006A320
```
