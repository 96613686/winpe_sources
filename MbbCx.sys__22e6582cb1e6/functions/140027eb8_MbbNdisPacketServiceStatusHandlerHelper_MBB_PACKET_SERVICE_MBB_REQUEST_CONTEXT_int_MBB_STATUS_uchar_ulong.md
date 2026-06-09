# MbbNdisPacketServiceStatusHandlerHelper<_MBB_PACKET_SERVICE>(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x140027eb8`
- end: `0x1400280f2`
- name: `??$MbbNdisPacketServiceStatusHandlerHelper@U_MBB_PACKET_SERVICE@@@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `570`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, int, unsigned int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x140031cc0`

## callees

- `0x140001db8`
- `0x1400051ac`
- `0x140005644`
- `0x140027eb8`
- `0x14002ec90`
- `0x14003f7e4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140027f5c`
- `ntoskrnl!ExAllocatePool2` at `0x140027f5c`

## pseudocode

```c
__int64 __fastcall MbbNdisPacketServiceStatusHandlerHelper<_MBB_PACKET_SERVICE>(
        struct _MBB_REQUEST_CONTEXT *a1,
        int a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5)
{
  __int64 v9; // r14
  unsigned int v10; // edi
  __int64 *v11; // rdx
  __int64 Pool2; // rax

  v9 = **((_QWORD **)a1 + 6);
  v10 = MbbUtilMbbToWwanStatus(a3);
  v11 = WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids;
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v11,
        3,
        93,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *((_DWORD *)a1 + 4),
        a2);
    }
LABEL_16:
    if ( v10 )
      v10 = MbbUtilMbbToWwanStatus(a3);
    goto LABEL_18;
  }
  if ( !a4 || a5 < 0x1C )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_Ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v11,
        3,
        94,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *((_DWORD *)a1 + 4),
        a5,
        28);
    }
    a2 = -1073676267;
    goto LABEL_16;
  }
  Pool2 = ExAllocatePool2(64, 44, 1683505741);
  if ( !Pool2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v11,
        3,
        95,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *((_DWORD *)a1 + 4));
    }
    a2 = -1073741670;
    goto LABEL_16;
  }
  *(_QWORD *)(Pool2 + 12) = 0;
  LODWORD(v11) = 44;
  *(_DWORD *)(Pool2 + 40) = 0;
  *(_DWORD *)Pool2 = 2883968;
  *(_QWORD *)(Pool2 + 24) = 0;
  *(_QWORD *)(Pool2 + 32) = 0;
  *(_DWORD *)(Pool2 + 20) = *(_DWORD *)(a4 + 8);
  *((_DWORD *)a1 + 183) = 44;
  *((_QWORD *)a1 + 92) = Pool2;
  *(_DWORD *)(Pool2 + 8) = *(_DWORD *)a4;
  *(_DWORD *)(Pool2 + 4) = v10;
  if ( !v10 )
  {
    *(_DWORD *)(Pool2 + 12) = *(_DWORD *)(a4 + 4);
    *(_QWORD *)(v9 + 1056) = *(_QWORD *)(a4 + 12);
    *(_QWORD *)(v9 + 1064) = *(_QWORD *)(a4 + 20);
    if ( *(_BYTE *)(v9 + 1072) )
    {
      *((_DWORD *)a1 + 182) |= 1u;
      *((_DWORD *)a1 + 186) = *(_DWORD *)(v9 + 1076);
    }
  }
LABEL_18:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v11,
      3,
      101,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *((_DWORD *)a1 + 4),
      v10);
  }
  MbbNdisIndicatePacketService(a1, a2, v10);
  return 0;
}

```

## disassembly

```asm
0x140027eb8  push    rbx
0x140027eba  push    rbp
0x140027ebb  push    rsi
0x140027ebc  push    rdi
0x140027ebd  push    r13
0x140027ebf  push    r14
0x140027ec1  push    r15
0x140027ec3  sub     rsp, 40h
0x140027ec7  mov     rax, [rcx+30h]
0x140027ecb  mov     rbx, rcx
0x140027ece  mov     ecx, r8d
0x140027ed1  mov     rsi, r9
0x140027ed4  mov     r15d, r8d
0x140027ed7  mov     ebp, edx
0x140027ed9  mov     r14, [rax]
0x140027edc  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140027ee1  lea     r13, WPP_RECORDER_INITIALIZED
0x140027ee8  mov     edi, eax
0x140027eea  lea     rdx, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140027ef1  mov     ecx, 3
0x140027ef6  test    ebp, ebp
0x140027ef8  jz      short loc_140027F35
0x140027efa  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140027f01  jz      loc_140028080
0x140027f07  mov     eax, [rbx+10h]
0x140027f0a  lea     r9d, [rcx+5Ah]
0x140027f0e  mov     r8d, ecx
0x140027f11  mov     [rsp+78h+var_48], ebp
0x140027f15  mov     rcx, cs:WPP_GLOBAL_Control
0x140027f1c  mov     [rsp+78h+var_50], eax
0x140027f20  mov     [rsp+78h+var_58], rdx
0x140027f25  mov     dl, 2
0x140027f27  mov     rcx, [rcx+40h]
0x140027f2b  call    WPP_RECORDER_SF_DD
0x140027f30  jmp     loc_140028080
0x140027f35  mov     eax, [rsp+78h+arg_20]
0x140027f3c  test    rsi, rsi
0x140027f3f  jz      loc_14002803F
0x140027f45  cmp     eax, 1Ch
0x140027f48  jb      loc_14002803F
0x140027f4e  mov     edx, 2Ch ; ','
0x140027f53  mov     r8d, 6458424Dh
0x140027f59  lea     ecx, [rdx+14h]
0x140027f5c  call    cs:__imp_ExAllocatePool2
0x140027f63  nop     dword ptr [rax+rax+00h]
0x140027f68  mov     rcx, rax
0x140027f6b  test    rax, rax
0x140027f6e  jnz     short loc_140027FB0
0x140027f70  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140027f77  lea     rsi, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140027f7e  jz      short loc_140027FA6
0x140027f80  lea     r8d, [rcx+3]
0x140027f84  mov     dl, 2
0x140027f86  mov     rcx, cs:WPP_GLOBAL_Control
0x140027f8d  lea     r9d, [rax+5Fh]
0x140027f91  mov     eax, [rbx+10h]
0x140027f94  mov     [rsp+78h+var_50], eax
0x140027f98  mov     [rsp+78h+var_58], rsi
0x140027f9d  mov     rcx, [rcx+40h]
0x140027fa1  call    WPP_RECORDER_SF_d
0x140027fa6  mov     ebp, 0C000009Ah
0x140027fab  jmp     loc_140028087
0x140027fb0  mov     qword ptr [rax+0Ch], 0
0x140027fb8  mov     edx, 2Ch ; ','
0x140027fbd  mov     dword ptr [rax+28h], 0
0x140027fc4  mov     dword ptr [rax], 2C0180h
0x140027fca  mov     qword ptr [rax+18h], 0
0x140027fd2  mov     qword ptr [rax+20h], 0
0x140027fda  mov     eax, [rsi+8]
0x140027fdd  mov     [rcx+14h], eax
0x140027fe0  mov     [rbx+2DCh], edx
0x140027fe6  mov     [rbx+2E0h], rcx
0x140027fed  mov     eax, [rsi]
0x140027fef  mov     [rcx+8], eax
0x140027ff2  mov     [rcx+4], edi
0x140027ff5  test    edi, edi
0x140027ff7  jnz     loc_140028097
0x140027ffd  mov     eax, [rsi+4]
0x140028000  mov     [rcx+0Ch], eax
0x140028003  mov     rax, [rsi+0Ch]
0x140028007  mov     [r14+420h], rax
0x14002800e  mov     rax, [rsi+14h]
0x140028012  lea     rsi, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140028019  mov     [r14+428h], rax
0x140028020  cmp     [r14+430h], dil
0x140028027  jz      short loc_14002809E
0x140028029  or      dword ptr [rbx+2D8h], 1
0x140028030  mov     eax, [r14+434h]
0x140028037  mov     [rbx+2E8h], eax
0x14002803d  jmp     short loc_14002809E
0x14002803f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140028046  jz      short loc_14002807B
0x140028048  mov     r8d, ecx
0x14002804b  mov     [rsp+78h+var_40], 1Ch
0x140028053  mov     rcx, cs:WPP_GLOBAL_Control
0x14002805a  mov     r9d, 5Eh ; '^'
0x140028060  mov     [rsp+78h+var_48], eax
0x140028064  mov     eax, [rbx+10h]
0x140028067  mov     [rsp+78h+var_50], eax
0x14002806b  mov     rcx, [rcx+40h]
0x14002806f  mov     [rsp+78h+var_58], rdx
0x140028074  mov     dl, 2
0x140028076  call    WPP_RECORDER_SF_Ddd
0x14002807b  mov     ebp, 0C0010015h
0x140028080  lea     rsi, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140028087  test    edi, edi
0x140028089  jz      short loc_14002809E
0x14002808b  mov     ecx, r15d
0x14002808e  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140028093  mov     edi, eax
0x140028095  jmp     short loc_14002809E
0x140028097  lea     rsi, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002809e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400280a5  jz      short loc_1400280D3
0x1400280a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400280ae  mov     r9d, 65h ; 'e'
0x1400280b4  mov     eax, [rbx+10h]
0x1400280b7  mov     dl, 4
0x1400280b9  mov     [rsp+78h+var_48], edi
0x1400280bd  mov     [rsp+78h+var_50], eax
0x1400280c1  mov     rcx, [rcx+40h]
0x1400280c5  lea     r8d, [r9-62h]
0x1400280c9  mov     [rsp+78h+var_58], rsi
0x1400280ce  call    WPP_RECORDER_SF_DD
0x1400280d3  mov     r8d, edi; unsigned int
0x1400280d6  mov     edx, ebp; int
0x1400280d8  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x1400280db  call    ?MbbNdisIndicatePacketService@@YAXPEAU_MBB_REQUEST_CONTEXT@@HK@Z; MbbNdisIndicatePacketService(_MBB_REQUEST_CONTEXT *,int,ulong)
0x1400280e0  xor     eax, eax
0x1400280e2  add     rsp, 40h
0x1400280e6  pop     r15
0x1400280e8  pop     r14
0x1400280ea  pop     r13
0x1400280ec  pop     rdi
0x1400280ed  pop     rsi
0x1400280ee  pop     rbp
0x1400280ef  pop     rbx
0x1400280f0  retn
```
