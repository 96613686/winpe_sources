# MbbNdisPacketServiceStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x140031cc0`
- end: `0x140031e13`
- name: `?MbbNdisPacketServiceStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `339`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x140001db8`
- `0x140027eb8`
- `0x1400280f8`
- `0x140028340`
- `0x140031cc0`

## pseudocode

```c
__int64 __fastcall MbbNdisPacketServiceStatusHandler(__int64 a1, int a2, unsigned int a3, __int64 a4, unsigned int a5)
{
  int v8; // ebp
  unsigned __int16 v9; // ax
  int v11; // [rsp+28h] [rbp-30h]
  int v12; // [rsp+28h] [rbp-30h]
  int v13; // [rsp+28h] [rbp-30h]

  v8 = a2;
  v9 = *(_WORD *)(**(_QWORD **)(a1 + 48) + 82LL);
  if ( v9 < 0x300u )
  {
    if ( v9 < 0x200u )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 4;
        v13 = *(_DWORD *)(a1 + 16);
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          3,
          92,
          (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
          v13);
      }
      return MbbNdisPacketServiceStatusHandlerHelper<_MBB_PACKET_SERVICE>(
               (struct _MBB_REQUEST_CONTEXT *)a1,
               v8,
               a3,
               a4,
               a5);
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 4;
        v12 = *(_DWORD *)(a1 + 16);
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          3,
          91,
          (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
          v12);
      }
      return MbbNdisPacketServiceStatusHandlerHelper<_MBB_PACKET_SERVICE_INFO_V2>(
               (struct _MBB_REQUEST_CONTEXT *)a1,
               v8,
               a3,
               a4,
               a5);
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      v11 = *(_DWORD *)(a1 + 16);
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        3,
        90,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        v11);
    }
    return MbbNdisPacketServiceStatusHandlerHelper<_MBB_PACKET_SERVICE_INFO_V3_AND_HIGHER>(
             (struct _MBB_REQUEST_CONTEXT *)a1,
             v8,
             a3,
             a4,
             a5);
  }
}

```

## disassembly

```asm
0x140031cc0  push    rbx
0x140031cc2  push    rbp
0x140031cc3  push    rsi
0x140031cc4  push    rdi
0x140031cc5  sub     rsp, 38h
0x140031cc9  mov     rax, [rcx+30h]
0x140031ccd  mov     rbx, rcx
0x140031cd0  mov     ecx, 300h
0x140031cd5  mov     rdi, r9
0x140031cd8  mov     esi, r8d
0x140031cdb  mov     ebp, edx
0x140031cdd  mov     r10, [rax]
0x140031ce0  movzx   eax, word ptr [r10+52h]
0x140031ce5  cmp     ax, cx
0x140031ce8  jb      short loc_140031D49
0x140031cea  lea     rax, WPP_RECORDER_INITIALIZED
0x140031cf1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031cf8  jz      short loc_140031D29
0x140031cfa  mov     eax, [rbx+10h]
0x140031cfd  mov     r9d, 5Ah ; 'Z'
0x140031d03  mov     rcx, cs:WPP_GLOBAL_Control
0x140031d0a  mov     dl, 4
0x140031d0c  mov     [rsp+58h+var_30], eax
0x140031d10  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140031d17  mov     qword ptr [rsp+58h+var_38], rax
0x140031d1c  lea     r8d, [r9-57h]
0x140031d20  mov     rcx, [rcx+40h]
0x140031d24  call    WPP_RECORDER_SF_d
0x140031d29  mov     eax, [rsp+58h+arg_20]
0x140031d30  mov     r9, rdi
0x140031d33  mov     r8d, esi
0x140031d36  mov     [rsp+58h+var_38], eax; int
0x140031d3a  mov     edx, ebp; int
0x140031d3c  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x140031d3f  call    ??$MbbNdisPacketServiceStatusHandlerHelper@U_MBB_PACKET_SERVICE_INFO_V3_AND_HIGHER@@@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbNdisPacketServiceStatusHandlerHelper<_MBB_PACKET_SERVICE_INFO_V3_AND_HIGHER>(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x140031d44  jmp     loc_140031E09
0x140031d49  mov     ecx, 200h
0x140031d4e  cmp     ax, cx
0x140031d51  jb      short loc_140031DAF
0x140031d53  lea     rax, WPP_RECORDER_INITIALIZED
0x140031d5a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031d61  jz      short loc_140031D92
0x140031d63  mov     eax, [rbx+10h]
0x140031d66  mov     r9d, 5Bh ; '['
0x140031d6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140031d73  mov     dl, 4
0x140031d75  mov     [rsp+58h+var_30], eax
0x140031d79  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140031d80  mov     qword ptr [rsp+58h+var_38], rax
0x140031d85  lea     r8d, [r9-58h]
0x140031d89  mov     rcx, [rcx+40h]
0x140031d8d  call    WPP_RECORDER_SF_d
0x140031d92  mov     eax, [rsp+58h+arg_20]
0x140031d99  mov     r9, rdi
0x140031d9c  mov     r8d, esi
0x140031d9f  mov     [rsp+58h+var_38], eax; int
0x140031da3  mov     edx, ebp; int
0x140031da5  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x140031da8  call    ??$MbbNdisPacketServiceStatusHandlerHelper@U_MBB_PACKET_SERVICE_INFO_V2@@@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbNdisPacketServiceStatusHandlerHelper<_MBB_PACKET_SERVICE_INFO_V2>(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x140031dad  jmp     short loc_140031E09
0x140031daf  lea     rax, WPP_RECORDER_INITIALIZED
0x140031db6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031dbd  jz      short loc_140031DEE
0x140031dbf  mov     eax, [rbx+10h]
0x140031dc2  mov     r9d, 5Ch ; '\'
0x140031dc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140031dcf  mov     dl, 4
0x140031dd1  mov     [rsp+58h+var_30], eax
0x140031dd5  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140031ddc  mov     qword ptr [rsp+58h+var_38], rax
0x140031de1  lea     r8d, [r9-59h]
0x140031de5  mov     rcx, [rcx+40h]
0x140031de9  call    WPP_RECORDER_SF_d
0x140031dee  mov     eax, [rsp+58h+arg_20]
0x140031df5  mov     r9, rdi
0x140031df8  mov     r8d, esi
0x140031dfb  mov     [rsp+58h+var_38], eax; int
0x140031dff  mov     edx, ebp; int
0x140031e01  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x140031e04  call    ??$MbbNdisPacketServiceStatusHandlerHelper@U_MBB_PACKET_SERVICE@@@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbNdisPacketServiceStatusHandlerHelper<_MBB_PACKET_SERVICE>(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x140031e09  add     rsp, 38h
0x140031e0d  pop     rdi
0x140031e0e  pop     rsi
0x140031e0f  pop     rbp
0x140031e10  pop     rbx
0x140031e11  retn
```
