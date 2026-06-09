# MbbNdisDssWrite(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)

- ea: `0x14000fe90`
- end: `0x14000ff77`
- name: `?MbbNdisDssWrite@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z`
- size: `231`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x140001db8`
- `0x1400051ac`
- `0x14000fe90`
- `0x140013ef0`
- `0x140019f78`

## pseudocode

```c
__int64 __fastcall MbbNdisDssWrite(struct _MBB_REQUEST_CONTEXT *a1, unsigned __int8 *a2, unsigned int *a3)
{
  unsigned int v4; // edi
  int v5; // edx
  int v7; // [rsp+28h] [rbp-20h]

  *a3 = 12;
  if ( *((_DWORD *)a2 + 2) )
  {
    _InterlockedIncrement((volatile signed __int32 *)a1 + 10);
    v4 = MbbNdisSendDssData(
           **((struct _MINIPORT_ADAPTER_CONTEXT ***)a1 + 6),
           a1,
           *((_DWORD *)a2 + 1),
           *((_DWORD *)a2 + 2),
           a2 + 12);
    if ( v4 )
    {
      MbbReqMgrDerefRequest(a1);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v5) = 2;
        WPP_RECORDER_SF_DD(
          WPP_GLOBAL_Control->DeviceExtension,
          v5,
          3,
          136,
          (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
          *((_DWORD *)a1 + 4),
          v4);
      }
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v7 = *((_DWORD *)a1 + 4);
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        3,
        135,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
        v7);
    }
    return (unsigned int)-1073676267;
  }
  return v4;
}

```

## disassembly

```asm
0x14000fe90  mov     [rsp+arg_0], rbx
0x14000fe95  push    rdi
0x14000fe96  sub     rsp, 40h
0x14000fe9a  mov     dword ptr [r8], 0Ch
0x14000fea1  mov     rbx, rcx
0x14000fea4  cmp     dword ptr [rdx+8], 0
0x14000fea8  jnz     short loc_14000FEF2
0x14000feaa  lea     rax, WPP_RECORDER_INITIALIZED
0x14000feb1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000feb8  jz      short loc_14000FEEB
0x14000feba  mov     eax, [rcx+10h]
0x14000febd  mov     r9d, 87h
0x14000fec3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000feca  mov     r8d, 3
0x14000fed0  mov     [rsp+48h+var_20], eax
0x14000fed4  mov     dl, 2
0x14000fed6  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x14000fedd  mov     [rsp+48h+var_28], rax
0x14000fee2  mov     rcx, [rcx+40h]
0x14000fee6  call    WPP_RECORDER_SF_d
0x14000feeb  mov     edi, 0C0010015h
0x14000fef0  jmp     short loc_14000FF69
0x14000fef2  lock inc dword ptr [rcx+28h]
0x14000fef6  mov     rcx, [rcx+30h]
0x14000fefa  lea     rax, [rdx+0Ch]
0x14000fefe  mov     r9d, [rdx+8]; unsigned int
0x14000ff02  mov     r8d, [rdx+4]; unsigned int
0x14000ff06  mov     rdx, rbx; struct _MBB_REQUEST_CONTEXT *
0x14000ff09  mov     [rsp+48h+var_28], rax; void *
0x14000ff0e  mov     rcx, [rcx]; struct _MINIPORT_ADAPTER_CONTEXT *
0x14000ff11  call    ?MbbNdisSendDssData@@YAJPEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_MBB_REQUEST_CONTEXT@@KKPEAX@Z; MbbNdisSendDssData(_MINIPORT_ADAPTER_CONTEXT *,_MBB_REQUEST_CONTEXT *,ulong,ulong,void *)
0x14000ff16  mov     edi, eax
0x14000ff18  test    eax, eax
0x14000ff1a  jz      short loc_14000FF69
0x14000ff1c  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x14000ff1f  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x14000ff24  lea     rax, WPP_RECORDER_INITIALIZED
0x14000ff2b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ff32  jz      short loc_14000FF69
0x14000ff34  mov     ecx, [rbx+10h]
0x14000ff37  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x14000ff3e  mov     [rsp+48h+var_18], edi
0x14000ff42  mov     r9d, 88h
0x14000ff48  mov     [rsp+48h+var_20], ecx
0x14000ff4c  mov     r8d, 3
0x14000ff52  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ff59  mov     dl, 2
0x14000ff5b  mov     [rsp+48h+var_28], rax
0x14000ff60  mov     rcx, [rcx+40h]
0x14000ff64  call    WPP_RECORDER_SF_DD
0x14000ff69  mov     rbx, [rsp+48h+arg_0]
0x14000ff6e  mov     eax, edi
0x14000ff70  add     rsp, 40h
0x14000ff74  pop     rdi
0x14000ff75  retn
```
