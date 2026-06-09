# MbbNdisPacketServiceStatusHandlerHelper<_MBB_PACKET_SERVICE_INFO_V2>(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x1400280f8`
- end: `0x140028337`
- name: `??$MbbNdisPacketServiceStatusHandlerHelper@U_MBB_PACKET_SERVICE_INFO_V2@@@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `575`
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
- `0x1400280f8`
- `0x14002ec90`
- `0x14003f7e4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002819c`
- `ntoskrnl!ExAllocatePool2` at `0x14002819c`

## pseudocode

```c
__int64 __fastcall MbbNdisPacketServiceStatusHandlerHelper<_MBB_PACKET_SERVICE_INFO_V2>(
        struct _MBB_REQUEST_CONTEXT *a1,
        int a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5)
{
  __int64 v9; // r14
  unsigned int v10; // esi
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
  if ( !a4 || a5 < 0x20 )
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
        32);
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
  *(_DWORD *)Pool2 = 2884224;
  *(_DWORD *)(Pool2 + 28) = 0;
  *(_QWORD *)(Pool2 + 32) = 0;
  *(_DWORD *)(Pool2 + 20) = *(_DWORD *)(a4 + 8);
  *(_DWORD *)(Pool2 + 24) = *(_DWORD *)(a4 + 28);
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
0x1400280f8  push    rbx
0x1400280fa  push    rbp
0x1400280fb  push    rsi
0x1400280fc  push    rdi
0x1400280fd  push    r13
0x1400280ff  push    r14
0x140028101  push    r15
0x140028103  sub     rsp, 40h
0x140028107  mov     rax, [rcx+30h]
0x14002810b  mov     rbx, rcx
0x14002810e  mov     ecx, r8d
0x140028111  mov     rdi, r9
0x140028114  mov     r15d, r8d
0x140028117  mov     ebp, edx
0x140028119  mov     r14, [rax]
0x14002811c  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140028121  lea     r13, WPP_RECORDER_INITIALIZED
0x140028128  mov     esi, eax
0x14002812a  lea     rdx, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140028131  mov     ecx, 3
0x140028136  test    ebp, ebp
0x140028138  jz      short loc_140028175
0x14002813a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140028141  jz      loc_1400282C5
0x140028147  mov     eax, [rbx+10h]
0x14002814a  lea     r9d, [rcx+5Ah]
0x14002814e  mov     r8d, ecx
0x140028151  mov     [rsp+78h+var_48], ebp
0x140028155  mov     rcx, cs:WPP_GLOBAL_Control
0x14002815c  mov     [rsp+78h+var_50], eax
0x140028160  mov     [rsp+78h+var_58], rdx
0x140028165  mov     dl, 2
0x140028167  mov     rcx, [rcx+40h]
0x14002816b  call    WPP_RECORDER_SF_DD
0x140028170  jmp     loc_1400282C5
0x140028175  mov     eax, [rsp+78h+arg_20]
0x14002817c  test    rdi, rdi
0x14002817f  jz      loc_140028284
0x140028185  cmp     eax, 20h ; ' '
0x140028188  jb      loc_140028284
0x14002818e  mov     edx, 2Ch ; ','
0x140028193  mov     r8d, 6458424Dh
0x140028199  lea     ecx, [rdx+14h]
0x14002819c  call    cs:__imp_ExAllocatePool2
0x1400281a3  nop     dword ptr [rax+rax+00h]
0x1400281a8  mov     rcx, rax
0x1400281ab  test    rax, rax
0x1400281ae  jnz     short loc_1400281F0
0x1400281b0  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400281b7  lea     rdi, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x1400281be  jz      short loc_1400281E6
0x1400281c0  lea     r8d, [rcx+3]
0x1400281c4  mov     dl, 2
0x1400281c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400281cd  lea     r9d, [rax+5Fh]
0x1400281d1  mov     eax, [rbx+10h]
0x1400281d4  mov     [rsp+78h+var_50], eax
0x1400281d8  mov     [rsp+78h+var_58], rdi
0x1400281dd  mov     rcx, [rcx+40h]
0x1400281e1  call    WPP_RECORDER_SF_d
0x1400281e6  mov     ebp, 0C000009Ah
0x1400281eb  jmp     loc_1400282CC
0x1400281f0  mov     qword ptr [rax+0Ch], 0
0x1400281f8  mov     edx, 2Ch ; ','
0x1400281fd  mov     dword ptr [rax+28h], 0
0x140028204  mov     dword ptr [rax], 2C0280h
0x14002820a  mov     dword ptr [rax+1Ch], 0
0x140028211  mov     qword ptr [rax+20h], 0
0x140028219  mov     eax, [rdi+8]
0x14002821c  mov     [rcx+14h], eax
0x14002821f  mov     eax, [rdi+1Ch]
0x140028222  mov     [rcx+18h], eax
0x140028225  mov     [rbx+2DCh], edx
0x14002822b  mov     [rbx+2E0h], rcx
0x140028232  mov     eax, [rdi]
0x140028234  mov     [rcx+8], eax
0x140028237  mov     [rcx+4], esi
0x14002823a  test    esi, esi
0x14002823c  jnz     loc_1400282DC
0x140028242  mov     eax, [rdi+4]
0x140028245  mov     [rcx+0Ch], eax
0x140028248  mov     rax, [rdi+0Ch]
0x14002824c  mov     [r14+420h], rax
0x140028253  mov     rax, [rdi+14h]
0x140028257  lea     rdi, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002825e  mov     [r14+428h], rax
0x140028265  cmp     [r14+430h], sil
0x14002826c  jz      short loc_1400282E3
0x14002826e  or      dword ptr [rbx+2D8h], 1
0x140028275  mov     eax, [r14+434h]
0x14002827c  mov     [rbx+2E8h], eax
0x140028282  jmp     short loc_1400282E3
0x140028284  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14002828b  jz      short loc_1400282C0
0x14002828d  mov     r8d, ecx
0x140028290  mov     [rsp+78h+var_40], 20h ; ' '
0x140028298  mov     rcx, cs:WPP_GLOBAL_Control
0x14002829f  mov     r9d, 5Eh ; '^'
0x1400282a5  mov     [rsp+78h+var_48], eax
0x1400282a9  mov     eax, [rbx+10h]
0x1400282ac  mov     [rsp+78h+var_50], eax
0x1400282b0  mov     rcx, [rcx+40h]
0x1400282b4  mov     [rsp+78h+var_58], rdx
0x1400282b9  mov     dl, 2
0x1400282bb  call    WPP_RECORDER_SF_Ddd
0x1400282c0  mov     ebp, 0C0010015h
0x1400282c5  lea     rdi, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x1400282cc  test    esi, esi
0x1400282ce  jz      short loc_1400282E3
0x1400282d0  mov     ecx, r15d
0x1400282d3  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x1400282d8  mov     esi, eax
0x1400282da  jmp     short loc_1400282E3
0x1400282dc  lea     rdi, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x1400282e3  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400282ea  jz      short loc_140028318
0x1400282ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400282f3  mov     r9d, 65h ; 'e'
0x1400282f9  mov     eax, [rbx+10h]
0x1400282fc  mov     dl, 4
0x1400282fe  mov     [rsp+78h+var_48], esi
0x140028302  mov     [rsp+78h+var_50], eax
0x140028306  mov     rcx, [rcx+40h]
0x14002830a  lea     r8d, [r9-62h]
0x14002830e  mov     [rsp+78h+var_58], rdi
0x140028313  call    WPP_RECORDER_SF_DD
0x140028318  mov     r8d, esi; unsigned int
0x14002831b  mov     edx, ebp; int
0x14002831d  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x140028320  call    ?MbbNdisIndicatePacketService@@YAXPEAU_MBB_REQUEST_CONTEXT@@HK@Z; MbbNdisIndicatePacketService(_MBB_REQUEST_CONTEXT *,int,ulong)
0x140028325  xor     eax, eax
0x140028327  add     rsp, 40h
0x14002832b  pop     r15
0x14002832d  pop     r14
0x14002832f  pop     r13
0x140028331  pop     rdi
0x140028332  pop     rsi
0x140028333  pop     rbp
0x140028334  pop     rbx
0x140028335  retn
```
