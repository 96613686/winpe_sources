# MbbNdisSubscribeDeviceServiceEvents(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)

- ea: `0x140017230`
- end: `0x140017499`
- name: `?MbbNdisSubscribeDeviceServiceEvents@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z`
- size: `617`
- prototype: `__int64 __fastcall(struct _MINIPORT_ADAPTER_CONTEXT ***, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callees

- `0x140001db8`
- `0x1400051ac`
- `0x140017230`
- `0x140018938`
- `0x14001ed10`
- `0x1400208bc`
- `0x14002373c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001744d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017472`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001744d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017472`

## pseudocode

```c
__int64 __fastcall MbbNdisSubscribeDeviceServiceEvents(
        struct _MINIPORT_ADAPTER_CONTEXT ***a1,
        unsigned __int8 *a2,
        unsigned int *a3)
{
  struct _MINIPORT_ADAPTER_CONTEXT **v5; // rdx
  unsigned int v6; // r8d
  unsigned int v8; // r10d
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdi
  unsigned int v11; // eax
  unsigned int v12; // edi
  int v13; // edx
  struct _MINIPORT_ADAPTER_CONTEXT **v14; // rcx
  int v15; // edx
  unsigned __int8 *v16; // rdx
  unsigned int v17; // r8d
  unsigned int v18; // eax
  int v19; // edx
  struct _MINIPORT_ADAPTER_CONTEXT **v20; // rcx
  struct _MINIPORT_ADAPTER_CONTEXT **v21; // rcx
  struct _MBB_SUBSCRIBE_EVENT_LIST *v23; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v24; // [rsp+78h] [rbp+28h] BYREF
  unsigned int v25; // [rsp+80h] [rbp+30h] BYREF
  struct _MBB_SUBSCRIBE_EVENT_LIST *v26; // [rsp+88h] [rbp+38h] BYREF

  v5 = 0;
  v6 = 0;
  v24 = 0;
  v26 = 0;
  v8 = *((_DWORD *)a2 + 2);
  v9 = *a3;
  v10 = 16LL * v8 + 12;
  v23 = 0;
  v25 = 0;
  if ( v9 < v10 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Ddi(WPP_GLOBAL_Control->DeviceExtension, 0, 0, (_DWORD)a2);
    v11 = -1;
    if ( v10 <= 0xFFFFFFFF )
      v11 = v10;
    *a3 = v11;
    v12 = -1073676268;
    goto LABEL_21;
  }
  if ( v8 )
  {
    v12 = MbbUtilWwanToMbbSubscribeEvents(*a1[6], (struct _GUID *)(a2 + 12), v8, 1, 0, 0, &v26, &v24);
    if ( v12 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          3,
          123,
          (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
          *((_DWORD *)a1 + 4));
      }
      goto LABEL_15;
    }
    v6 = v24;
    v5 = (struct _MINIPORT_ADAPTER_CONTEXT **)v26;
  }
  v14 = a1[6];
  a1[91] = v5;
  *((_DWORD *)a1 + 184) = v6;
  a1[71] = v5;
  v12 = MbbUtilGenerateFullPowerSubscribeEventList(*v14, (struct _MBB_SUBSCRIBE_EVENT_LIST *)v5, v6, &v23, &v25);
  if ( v12 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v15,
        3,
        124,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
        *((_DWORD *)a1 + 4),
        v12);
    }
LABEL_15:
    if ( v12 == 259 )
      return v12;
    goto LABEL_21;
  }
  v16 = (unsigned __int8 *)v23;
  v17 = v25;
  a1[70] = (struct _MINIPORT_ADAPTER_CONTEXT **)v23;
  v18 = MbbUtilSetAttributeWithParameter((struct _MBB_REQUEST_CONTEXT *)a1, v16, v17);
  v12 = v18;
  if ( !v18 || v18 == 259 )
    return v12;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v19) = 2;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v19,
      3,
      125,
      (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
      *((_DWORD *)a1 + 4),
      v18);
  }
LABEL_21:
  v20 = a1[70];
  if ( v20 )
  {
    ExFreePoolWithTag(v20, 0);
    a1[70] = 0;
  }
  v21 = a1[71];
  if ( v21 )
  {
    ExFreePoolWithTag(v21, 0);
    a1[71] = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x140017230  mov     [rsp-18h+arg_0], rbx
0x140017235  push    rbp
0x140017236  push    rsi
0x140017237  push    rdi
0x140017238  mov     rbp, rsp
0x14001723b  sub     rsp, 50h
0x14001723f  mov     r9, rdx
0x140017242  mov     rsi, r8
0x140017245  xor     edx, edx
0x140017247  xor     r8d, r8d
0x14001724a  mov     rbx, rcx
0x14001724d  mov     [rbp+arg_8], r8d
0x140017251  mov     [rbp+arg_18], rdx
0x140017255  mov     r10d, [r9+8]
0x140017259  mov     ecx, [rsi]
0x14001725b  mov     edi, r10d
0x14001725e  shl     rdi, 4
0x140017262  add     rdi, 0Ch
0x140017266  mov     [rbp+var_10], rdx
0x14001726a  mov     [rbp+arg_10], edx
0x14001726d  cmp     rcx, rdi
0x140017270  jnb     short loc_1400172BA
0x140017272  lea     rax, WPP_RECORDER_INITIALIZED
0x140017279  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017280  jz      short loc_1400172A2
0x140017282  mov     eax, [rbx+10h]
0x140017285  mov     [rsp+50h+var_18], rdi
0x14001728a  mov     dword ptr [rsp+50h+var_20], ecx
0x14001728e  mov     rcx, cs:WPP_GLOBAL_Control
0x140017295  mov     [rsp+50h+var_28], eax
0x140017299  mov     rcx, [rcx+40h]
0x14001729d  call    WPP_RECORDER_SF_Ddi
0x1400172a2  mov     eax, 0FFFFFFFFh
0x1400172a7  cmp     rdi, rax
0x1400172aa  ja      short loc_1400172AE
0x1400172ac  mov     eax, edi
0x1400172ae  mov     [rsi], eax
0x1400172b0  mov     edi, 0C0010014h
0x1400172b5  jmp     loc_14001743F
0x1400172ba  test    r10d, r10d
0x1400172bd  jz      loc_14001734B
0x1400172c3  mov     rcx, [rbx+30h]
0x1400172c7  lea     rax, [rbp+arg_8]
0x1400172cb  mov     [rsp+50h+var_18], rax; unsigned int *
0x1400172d0  lea     rdx, [r9+0Ch]; struct _GUID *
0x1400172d4  lea     rax, [rbp+arg_18]
0x1400172d8  mov     r9d, 1; int
0x1400172de  mov     [rsp+50h+var_20], rax; struct _MBB_SUBSCRIBE_EVENT_LIST **
0x1400172e3  mov     rcx, [rcx]; struct _MINIPORT_ADAPTER_CONTEXT *
0x1400172e6  mov     [rsp+50h+var_28], r8d; unsigned int
0x1400172eb  mov     [rsp+50h+var_30], r8; struct _MBB_SUBSCRIBE_EVENT_LIST *
0x1400172f0  mov     r8d, r10d; unsigned int
0x1400172f3  call    ?MbbUtilWwanToMbbSubscribeEvents@@YAHPEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_GUID@@KHPEAU_MBB_SUBSCRIBE_EVENT_LIST@@KPEAPEAU3@PEAK@Z; MbbUtilWwanToMbbSubscribeEvents(_MINIPORT_ADAPTER_CONTEXT *,_GUID *,ulong,int,_MBB_SUBSCRIBE_EVENT_LIST *,ulong,_MBB_SUBSCRIBE_EVENT_LIST * *,ulong *)
0x1400172f8  mov     edi, eax
0x1400172fa  test    eax, eax
0x1400172fc  jz      short loc_140017343
0x1400172fe  lea     rax, WPP_RECORDER_INITIALIZED
0x140017305  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001730c  jz      loc_1400173C2
0x140017312  mov     ecx, [rbx+10h]
0x140017315  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x14001731c  mov     [rsp+50h+var_28], ecx
0x140017320  mov     r9d, 7Bh ; '{'
0x140017326  mov     rcx, cs:WPP_GLOBAL_Control
0x14001732d  mov     dl, 2
0x14001732f  mov     [rsp+50h+var_30], rax
0x140017334  lea     r8d, [r9-78h]
0x140017338  mov     rcx, [rcx+40h]
0x14001733c  call    WPP_RECORDER_SF_d
0x140017341  jmp     short loc_1400173C2
0x140017343  mov     r8d, [rbp+arg_8]; unsigned int
0x140017347  mov     rdx, [rbp+arg_18]; struct _MBB_SUBSCRIBE_EVENT_LIST *
0x14001734b  mov     rcx, [rbx+30h]
0x14001734f  lea     rax, [rbp+arg_10]
0x140017353  mov     [rbx+2D8h], rdx
0x14001735a  lea     r9, [rbp+var_10]; struct _MBB_SUBSCRIBE_EVENT_LIST **
0x14001735e  mov     [rbx+2E0h], r8d
0x140017365  mov     [rbx+238h], rdx
0x14001736c  mov     rcx, [rcx]; struct _MINIPORT_ADAPTER_CONTEXT *
0x14001736f  mov     [rsp+50h+var_30], rax; unsigned int *
0x140017374  call    ?MbbUtilGenerateFullPowerSubscribeEventList@@YAHPEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_MBB_SUBSCRIBE_EVENT_LIST@@KPEAPEAU2@PEAK@Z; MbbUtilGenerateFullPowerSubscribeEventList(_MINIPORT_ADAPTER_CONTEXT *,_MBB_SUBSCRIBE_EVENT_LIST *,ulong,_MBB_SUBSCRIBE_EVENT_LIST * *,ulong *)
0x140017379  mov     edi, eax
0x14001737b  test    eax, eax
0x14001737d  jz      short loc_1400173D0
0x14001737f  lea     rax, WPP_RECORDER_INITIALIZED
0x140017386  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001738d  jz      short loc_1400173C2
0x14001738f  mov     eax, [rbx+10h]
0x140017392  mov     r9d, 7Ch ; '|'
0x140017398  mov     rcx, cs:WPP_GLOBAL_Control
0x14001739f  mov     dl, 2
0x1400173a1  mov     dword ptr [rsp+50h+var_20], edi
0x1400173a5  mov     [rsp+50h+var_28], eax
0x1400173a9  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x1400173b0  lea     r8d, [r9-79h]
0x1400173b4  mov     [rsp+50h+var_30], rax
0x1400173b9  mov     rcx, [rcx+40h]
0x1400173bd  call    WPP_RECORDER_SF_DD
0x1400173c2  cmp     edi, 103h
0x1400173c8  jz      loc_140017489
0x1400173ce  jmp     short loc_14001743F
0x1400173d0  mov     rdx, [rbp+var_10]; unsigned __int8 *
0x1400173d4  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x1400173d7  mov     r8d, [rbp+arg_10]; unsigned int
0x1400173db  mov     [rbx+230h], rdx
0x1400173e2  call    ?MbbUtilSetAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilSetAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x1400173e7  mov     edi, eax
0x1400173e9  test    eax, eax
0x1400173eb  jz      loc_140017489
0x1400173f1  cmp     eax, 103h
0x1400173f6  jz      loc_140017489
0x1400173fc  lea     rax, WPP_RECORDER_INITIALIZED
0x140017403  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001740a  jz      short loc_14001743F
0x14001740c  mov     eax, [rbx+10h]
0x14001740f  mov     r9d, 7Dh ; '}'
0x140017415  mov     rcx, cs:WPP_GLOBAL_Control
0x14001741c  mov     dl, 2
0x14001741e  mov     dword ptr [rsp+50h+var_20], edi
0x140017422  mov     [rsp+50h+var_28], eax
0x140017426  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x14001742d  lea     r8d, [r9-7Ah]
0x140017431  mov     [rsp+50h+var_30], rax
0x140017436  mov     rcx, [rcx+40h]
0x14001743a  call    WPP_RECORDER_SF_DD
0x14001743f  mov     rcx, [rbx+230h]; P
0x140017446  test    rcx, rcx
0x140017449  jz      short loc_140017464
0x14001744b  xor     edx, edx; Tag
0x14001744d  call    cs:__imp_ExFreePoolWithTag
0x140017454  nop     dword ptr [rax+rax+00h]
0x140017459  mov     qword ptr [rbx+230h], 0
0x140017464  mov     rcx, [rbx+238h]; P
0x14001746b  test    rcx, rcx
0x14001746e  jz      short loc_140017489
0x140017470  xor     edx, edx; Tag
0x140017472  call    cs:__imp_ExFreePoolWithTag
0x140017479  nop     dword ptr [rax+rax+00h]
0x14001747e  mov     qword ptr [rbx+238h], 0
0x140017489  mov     rbx, [rsp+50h+arg_0]
0x14001748e  mov     eax, edi
0x140017490  add     rsp, 50h
0x140017494  pop     rdi
0x140017495  pop     rsi
0x140017496  pop     rbp
0x140017497  retn
```
