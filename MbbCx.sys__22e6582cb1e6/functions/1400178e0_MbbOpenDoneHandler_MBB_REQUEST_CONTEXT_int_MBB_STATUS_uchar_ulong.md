# MbbOpenDoneHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x1400178e0`
- end: `0x140017a8d`
- name: `?MbbOpenDoneHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x140001db8`
- `0x1400051ac`
- `0x1400178e0`
- `0x140018bc0`
- `0x140024338`

## pseudocode

```c
__int64 __fastcall MbbOpenDoneHandler(__int64 a1, unsigned int a2, __int64 a3, _DWORD *a4, unsigned int a5)
{
  unsigned int v5; // edi
  _DWORD *v6; // rbx
  int v7; // edx
  __int64 v9; // [rsp+28h] [rbp-40h]
  char v10; // [rsp+30h] [rbp-38h]

  v5 = a2;
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v10 = a2;
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        3,
        164,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
        *(_DWORD *)(a1 + 16),
        v10);
    }
  }
  else if ( a5 >= 0x10 )
  {
    if ( *a4 == -2147483647 && a4[1] >= 0x10u )
    {
      v6 = a4 + 3;
      MbbWriteEventOpn(&MBIM_UINT32_PAYLOAD_MSG, (LPCGUID)(a1 + 24), 0, 4u, a4, 4, a4 + 1, 4, a4 + 2, 4, a4 + 3, 4);
      if ( *v6 )
      {
        v5 = -1073741514;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v9) = *v6;
          LOBYTE(v7) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v7,
            3,
            167,
            (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
            v9);
        }
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_LDDD(WPP_GLOBAL_Control->DeviceExtension, *a4, a1, (_DWORD)a4);
      return (unsigned int)-1071448043;
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        3,
        165,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
        a5);
    }
    return (unsigned int)-1071448044;
  }
  return v5;
}

```

## disassembly

```asm
0x1400178e0  mov     [rsp+arg_0], rbx
0x1400178e5  push    rdi
0x1400178e6  sub     rsp, 60h
0x1400178ea  mov     edi, edx
0x1400178ec  mov     r8, rcx
0x1400178ef  test    edx, edx
0x1400178f1  jz      short loc_140017941
0x1400178f3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400178fa  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017901  jz      loc_140017A7F
0x140017907  mov     eax, [rcx+10h]
0x14001790a  mov     r9d, 0A4h
0x140017910  mov     rcx, cs:WPP_GLOBAL_Control
0x140017917  mov     r8d, 3
0x14001791d  mov     dword ptr [rsp+68h+var_38], edx
0x140017921  mov     dl, 2
0x140017923  mov     dword ptr [rsp+68h+var_40], eax
0x140017927  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x14001792e  mov     [rsp+68h+var_48], rax
0x140017933  mov     rcx, [rcx+40h]
0x140017937  call    WPP_RECORDER_SF_DD
0x14001793c  jmp     loc_140017A7F
0x140017941  mov     ecx, [rsp+68h+arg_20]
0x140017948  cmp     ecx, 10h
0x14001794b  jnb     short loc_140017995
0x14001794d  lea     rax, WPP_RECORDER_INITIALIZED
0x140017954  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001795b  jz      short loc_14001798B
0x14001795d  mov     dword ptr [rsp+68h+var_40], ecx
0x140017961  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x140017968  mov     rcx, cs:WPP_GLOBAL_Control
0x14001796f  mov     r9d, 0A5h
0x140017975  mov     r8d, 3
0x14001797b  mov     [rsp+68h+var_48], rax
0x140017980  mov     dl, 2
0x140017982  mov     rcx, [rcx+40h]
0x140017986  call    WPP_RECORDER_SF_d
0x14001798b  mov     edi, 0C0230014h
0x140017990  jmp     loc_140017A7F
0x140017995  mov     edx, [r9]
0x140017998  lea     rcx, [r9+4]
0x14001799c  cmp     edx, 80000001h
0x1400179a2  jnz     loc_140017A48
0x1400179a8  cmp     dword ptr [rcx], 10h
0x1400179ab  jb      loc_140017A48
0x1400179b1  mov     r10d, 4
0x1400179b7  lea     rbx, [r9+0Ch]
0x1400179bb  mov     [rsp+68h+var_10], r10
0x1400179c0  lea     rax, [r9+8]
0x1400179c4  mov     [rsp+68h+var_18], rbx
0x1400179c9  lea     rdx, [r8+18h]; ActivityId
0x1400179cd  mov     [rsp+68h+var_20], r10
0x1400179d2  xor     r8d, r8d; RelatedActivityId
0x1400179d5  mov     [rsp+68h+var_28], rax
0x1400179da  mov     [rsp+68h+var_30], r10
0x1400179df  mov     [rsp+68h+var_38], rcx
0x1400179e4  lea     rcx, MBIM_UINT32_PAYLOAD_MSG; EventDescriptor
0x1400179eb  mov     [rsp+68h+var_40], r10
0x1400179f0  mov     [rsp+68h+var_48], r9
0x1400179f5  mov     r9d, r10d; unsigned __int16
0x1400179f8  call    ?MbbWriteEventOpn@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@1GZZ; MbbWriteEventOpn(_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,...)
0x1400179fd  mov     ecx, [rbx]
0x1400179ff  test    ecx, ecx
0x140017a01  jz      short loc_140017A7F
0x140017a03  mov     edi, 0C0000136h
0x140017a08  lea     rax, WPP_RECORDER_INITIALIZED
0x140017a0f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017a16  jz      short loc_140017A7F
0x140017a18  mov     dword ptr [rsp+68h+var_40], ecx
0x140017a1c  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x140017a23  mov     rcx, cs:WPP_GLOBAL_Control
0x140017a2a  mov     r9d, 0A7h
0x140017a30  mov     r8d, 3
0x140017a36  mov     [rsp+68h+var_48], rax
0x140017a3b  mov     dl, 2
0x140017a3d  mov     rcx, [rcx+40h]
0x140017a41  call    WPP_RECORDER_SF_d
0x140017a46  jmp     short loc_140017A7F
0x140017a48  lea     rax, WPP_RECORDER_INITIALIZED
0x140017a4f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017a56  jz      short loc_140017A7A
0x140017a58  mov     eax, [r9+8]
0x140017a5c  mov     dword ptr [rsp+68h+var_30], eax
0x140017a60  mov     eax, [rcx]
0x140017a62  mov     rcx, cs:WPP_GLOBAL_Control
0x140017a69  mov     dword ptr [rsp+68h+var_38], eax
0x140017a6d  mov     dword ptr [rsp+68h+var_40], edx
0x140017a71  mov     rcx, [rcx+40h]
0x140017a75  call    WPP_RECORDER_SF_LDDD
0x140017a7a  mov     edi, 0C0230015h
0x140017a7f  mov     rbx, [rsp+68h+arg_0]
0x140017a84  mov     eax, edi
0x140017a86  add     rsp, 60h
0x140017a8a  pop     rdi
0x140017a8b  retn
```
