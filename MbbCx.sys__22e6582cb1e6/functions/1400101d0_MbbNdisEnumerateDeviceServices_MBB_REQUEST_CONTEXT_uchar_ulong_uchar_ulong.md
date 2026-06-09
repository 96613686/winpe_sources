# MbbNdisEnumerateDeviceServices(_MBB_REQUEST_CONTEXT *,uchar *,ulong *,uchar *,ulong *)

- ea: `0x1400101d0`
- end: `0x14001040d`
- name: `?MbbNdisEnumerateDeviceServices@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK12@Z`
- size: `573`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callees

- `0x1400051ac`
- `0x140005644`
- `0x1400101d0`
- `0x14001f5b8`
- `0x14003f994`
- `0x140047e50`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001022f`
- `ntoskrnl!ExAllocatePool2` at `0x14001022f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400103db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400103db`

## pseudocode

```c
__int64 __fastcall MbbNdisEnumerateDeviceServices(
        struct _MBB_REQUEST_CONTEXT *a1,
        unsigned __int8 *a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  __int64 v5; // r13
  unsigned int v6; // r15d
  __int64 Pool2; // rax
  __int64 v8; // rdx
  _DWORD *v9; // rbx
  __int64 v11; // r12
  unsigned int v12; // r14d
  __int64 v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rax
  int v16; // ecx
  struct _NDIS_STATUS_INDICATION v17; // [rsp+40h] [rbp-71h] BYREF

  memset(&v17, 0, sizeof(v17));
  v5 = **((_QWORD **)a1 + 6);
  v6 = *(_DWORD *)(v5 + 1104);
  Pool2 = ExAllocatePool2(64, 24 * v6 + 28, 1683505741);
  v9 = (_DWORD *)Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = 1835392;
    v11 = 0;
    v12 = 0;
    *(_DWORD *)(Pool2 + 8) = *(_DWORD *)(v5 + 84);
    *(_DWORD *)(Pool2 + 16) = *(_DWORD *)(v5 + 1120);
    *(_DWORD *)(Pool2 + 12) = 0x10000;
    *(_QWORD *)(Pool2 + 20) = 9;
    if ( v6 )
    {
      v13 = 0;
      do
      {
        if ( !MbbUtilIsNativeMbnService((struct _GUID *)&v9[6 * v13 + 7]) )
        {
          v8 = *(_QWORD *)(v5 + 1112);
          v14 = 3 * v11;
          *(_OWORD *)&v9[2 * v14 + 7] = *(_OWORD *)(v8 + 40 * v13);
          v9[2 * v14 + 11] = *(_DWORD *)(v8 + 40 * v13 + 16);
          v9[2 * v14 + 12] = *(_DWORD *)(v8 + 40 * v13 + 20);
          ++v9[6];
          v11 = (unsigned int)(v11 + 1);
        }
        ++v12;
        ++v13;
      }
      while ( v12 < v6 );
    }
    v15 = *((_QWORD *)a1 + 6);
    v17.Header = (NDIS_OBJECT_HEADER)7340440;
    v16 = v9[6];
    v17.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v15 + 1144LL) + 16LL);
    v17.DestinationHandle = (NDIS_HANDLE)*((_QWORD *)a1 + 55);
    v17.RequestId = (PVOID)*((_QWORD *)a1 + 54);
    v17.PortNumber = 0;
    v17.StatusBufferSize = 24 * v16 + 28;
    *(_QWORD *)&v17.StatusCode = 1074008086;
    v17.Guid = 0;
    v17.StatusBuffer = v9;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 4;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        3,
        55,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
        *((_DWORD *)a1 + 4),
        v16);
    }
    MbbUtilNdisMiniportIndicateStatusEx(**(NDIS_HANDLE ***)(**((_QWORD **)a1 + 6) + 1144LL), &v17);
    ExFreePoolWithTag(v9, 0);
    return 65537;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_Ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        3,
        54,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
        *((_DWORD *)a1 + 4),
        24 * v6 + 28,
        v6);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x1400101d0  push    rbp
0x1400101d2  push    rbx
0x1400101d3  push    rsi
0x1400101d4  push    rdi
0x1400101d5  push    r12
0x1400101d7  push    r13
0x1400101d9  push    r14
0x1400101db  push    r15
0x1400101dd  lea     rbp, [rsp-17h]
0x1400101e2  sub     rsp, 0C8h
0x1400101e9  mov     rax, cs:__security_cookie
0x1400101f0  xor     rax, rsp
0x1400101f3  mov     [rbp+4Fh+var_50], rax
0x1400101f7  xor     edx, edx; Val
0x1400101f9  mov     rsi, rcx
0x1400101fc  lea     rcx, [rbp+4Fh+var_C0]; void *
0x140010200  lea     r8d, [rdx+70h]; Size
0x140010204  call    memset
0x140010209  mov     rax, [rsi+30h]
0x14001020d  mov     ecx, 40h ; '@'
0x140010212  mov     r8d, 6458424Dh
0x140010218  mov     r13, [rax]
0x14001021b  mov     r15d, [r13+450h]
0x140010222  lea     eax, [r15+r15*2]
0x140010226  lea     edi, ds:1Ch[rax*8]
0x14001022d  mov     edx, edi
0x14001022f  call    cs:__imp_ExAllocatePool2
0x140010236  nop     dword ptr [rax+rax+00h]
0x14001023b  mov     rbx, rax
0x14001023e  test    rax, rax
0x140010241  jnz     short loc_140010293
0x140010243  lea     rax, WPP_RECORDER_INITIALIZED
0x14001024a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010251  jz      short loc_140010289
0x140010253  mov     eax, [rsi+10h]
0x140010256  lea     r9d, [rbx+36h]
0x14001025a  mov     rcx, cs:WPP_GLOBAL_Control
0x140010261  lea     r8d, [rbx+3]
0x140010265  mov     [rsp+100h+var_C8], r15d
0x14001026a  mov     dl, 2
0x14001026c  mov     [rsp+100h+var_D0], edi
0x140010270  mov     [rsp+100h+var_D8], eax
0x140010274  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x14001027b  mov     rcx, [rcx+40h]
0x14001027f  mov     [rsp+100h+var_E0], rax
0x140010284  call    WPP_RECORDER_SF_Ddd
0x140010289  mov     eax, 0C000009Ah
0x14001028e  jmp     loc_1400103EC
0x140010293  mov     qword ptr [rax], 1C0180h
0x14001029a  xor     r12d, r12d
0x14001029d  mov     eax, [r13+54h]
0x1400102a1  xor     r14d, r14d
0x1400102a4  mov     [rbx+8], eax
0x1400102a7  mov     eax, [r13+460h]
0x1400102ae  mov     [rbx+10h], eax
0x1400102b1  mov     dword ptr [rbx+0Ch], 10000h
0x1400102b8  mov     qword ptr [rbx+14h], 9
0x1400102c0  test    r15d, r15d
0x1400102c3  jz      short loc_140010319
0x1400102c5  xor     edi, edi
0x1400102c7  lea     rax, [rdi+rdi*2]
0x1400102cb  lea     rcx, [rbx+1Ch]
0x1400102cf  lea     rcx, [rcx+rax*8]; Source2
0x1400102d3  call    ?MbbUtilIsNativeMbnService@@YAEPEAU_GUID@@@Z; MbbUtilIsNativeMbnService(_GUID *)
0x1400102d8  test    al, al
0x1400102da  jnz     short loc_14001030E
0x1400102dc  mov     rdx, [r13+458h]
0x1400102e3  lea     rcx, [r12+r12*2]
0x1400102e7  lea     r8, [rdi+rdi*4]
0x1400102eb  movups  xmm0, xmmword ptr [rdx+r8*8]
0x1400102f0  movdqu  xmmword ptr [rbx+rcx*8+1Ch], xmm0
0x1400102f6  mov     eax, [rdx+r8*8+10h]
0x1400102fb  mov     [rbx+rcx*8+2Ch], eax
0x1400102ff  mov     eax, [rdx+r8*8+14h]
0x140010304  mov     [rbx+rcx*8+30h], eax
0x140010308  inc     dword ptr [rbx+18h]
0x14001030b  inc     r12d
0x14001030e  inc     r14d
0x140010311  inc     rdi
0x140010314  cmp     r14d, r15d
0x140010317  jb      short loc_1400102C7
0x140010319  mov     rax, [rsi+30h]
0x14001031d  xorps   xmm0, xmm0
0x140010320  mov     dword ptr [rbp+4Fh+var_C0.Header.Type], 700198h
0x140010327  mov     rcx, [rax]
0x14001032a  mov     rax, [rcx+478h]
0x140010331  mov     rcx, [rax]
0x140010334  mov     rax, [rcx+10h]
0x140010338  mov     ecx, [rbx+18h]
0x14001033b  mov     [rbp+4Fh+var_C0.SourceHandle], rax
0x14001033f  mov     rax, [rsi+1B8h]
0x140010346  mov     [rbp+4Fh+var_C0.DestinationHandle], rax
0x14001034a  mov     rax, [rsi+1B0h]
0x140010351  mov     [rbp+4Fh+var_C0.RequestId], rax
0x140010355  lea     eax, [rcx+rcx*2]
0x140010358  lea     eax, ds:1Ch[rax*8]
0x14001035f  mov     [rbp+4Fh+var_C0.PortNumber], 0
0x140010366  mov     [rbp+4Fh+var_C0.StatusBufferSize], eax
0x140010369  mov     qword ptr [rbp+4Fh+var_C0.StatusCode], 40041016h
0x140010371  movups  xmmword ptr [rbp+4Fh+var_C0.Guid.Data1], xmm0
0x140010375  mov     [rbp+4Fh+var_C0.StatusBuffer], rbx
0x140010379  lea     rax, WPP_RECORDER_INITIALIZED
0x140010380  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010387  jz      short loc_1400103BC
0x140010389  mov     eax, [rsi+10h]
0x14001038c  mov     r9d, 37h ; '7'
0x140010392  mov     [rsp+100h+var_D0], ecx
0x140010396  mov     dl, 4
0x140010398  mov     rcx, cs:WPP_GLOBAL_Control
0x14001039f  mov     [rsp+100h+var_D8], eax
0x1400103a3  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x1400103aa  lea     r8d, [r9-34h]
0x1400103ae  mov     [rsp+100h+var_E0], rax
0x1400103b3  mov     rcx, [rcx+40h]
0x1400103b7  call    WPP_RECORDER_SF_DD
0x1400103bc  mov     rax, [rsi+30h]
0x1400103c0  mov     rdx, [rax]
0x1400103c3  mov     rcx, [rdx+478h]
0x1400103ca  lea     rdx, [rbp+4Fh+var_C0]; struct _NDIS_STATUS_INDICATION *
0x1400103ce  mov     rcx, [rcx]; struct _MINIPORT_INTERFACE_CONTEXT *
0x1400103d1  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x1400103d6  xor     edx, edx; Tag
0x1400103d8  mov     rcx, rbx; P
0x1400103db  call    cs:__imp_ExFreePoolWithTag
0x1400103e2  nop     dword ptr [rax+rax+00h]
0x1400103e7  mov     eax, 10001h
0x1400103ec  mov     rcx, [rbp+4Fh+var_50]
0x1400103f0  xor     rcx, rsp; StackCookie
0x1400103f3  call    __security_check_cookie
0x1400103f8  add     rsp, 0C8h
0x1400103ff  pop     r15
0x140010401  pop     r14
0x140010403  pop     r13
0x140010405  pop     r12
0x140010407  pop     rdi
0x140010408  pop     rsi
0x140010409  pop     rbx
0x14001040a  pop     rbp
0x14001040b  retn
```
