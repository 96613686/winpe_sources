# DtcWriteToEventLoggerExW(ushort,ushort,ulong,void *,ushort,ulong,ushort const * *,void *,int)

- ea: `0x180070f24`
- end: `0x1800711cc`
- name: `?DtcWriteToEventLoggerExW@@YAJGGKPEAXGKPEAPEBG0H@Z`
- size: `680`
- prototype: `__int64 __fastcall(unsigned __int16, unsigned __int16, unsigned int, void *, unsigned __int16, size_t Size, const unsigned __int16 **, void *Src, int)`
- caller_count: `13`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f6c0`
- `0x18000f8d0`
- `0x180010110`
- `0x180010d88`
- `0x18001b5b0`
- `0x18001f6b0`
- `0x18001fac0`
- `0x18003c880`
- `0x1800592a8`
- `0x1800594e0`
- `0x18006e22c`
- `0x180072804`
- `0x18007436c`

## callees

- `0x18000d814`
- `0x18001de26`
- `0x180070b84`
- `0x180070c2c`
- `0x180070cd4`
- `0x180070f24`
- `0x1800773a0`
- `0x18008179c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800711aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800711b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800711aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800711b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071091`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071091`

## pseudocode

```c
int __fastcall DtcWriteToEventLoggerExW(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        void *a4,
        unsigned __int16 a5,
        size_t Size,
        unsigned __int16 **a7,
        void *Src,
        int a9)
{
  int v9; // ebx
  unsigned __int16 *v10; // r14
  unsigned int v11; // eax
  unsigned int LocalDTCProfileInt; // eax
  int v14; // r15d
  void *v15; // r12
  void *v16; // rdi
  void *v17; // r9
  int ServiceNameFromTmInstance; // eax
  __int64 v19; // rax
  void *v20; // rsi
  unsigned int v21; // r13d
  size_t v22; // rbp
  unsigned int v23; // ebx
  char *v24; // r15
  size_t v25; // rax
  size_t v26; // rbx
  unsigned int v27; // r13d
  int v28; // eax
  unsigned __int16 v29; // [rsp+B0h] [rbp+8h]
  unsigned __int16 v30; // [rsp+B8h] [rbp+10h]
  unsigned int v31; // [rsp+C0h] [rbp+18h]
  unsigned __int16 *v32; // [rsp+C8h] [rbp+20h] BYREF

  v31 = a3;
  v30 = a2;
  v29 = a1;
  v9 = 0;
  v32 = 0;
  v10 = 0;
  v11 = g_dwDuplicateEventFilterTimeout;
  if ( g_dwDuplicateEventFilterTimeout == -1 )
  {
    LocalDTCProfileInt = GetLocalDTCProfileInt("SuppressDuplicateDuration", 0x5265C00u);
    a3 = v31;
    a2 = v30;
    a1 = v29;
    g_dwDuplicateEventFilterTimeout = LocalDTCProfileInt;
    if ( LocalDTCProfileInt )
      goto LABEL_6;
    v11 = 0;
    g_dwDuplicateEventFilterTimeout = 0;
  }
  if ( !v11 )
    return DtcWriteToEventLoggerExUnFilteredW(a1, a2, a3, a4, a5, Size, (const unsigned __int16 **)a7, Src, a9);
LABEL_6:
  v14 = a9;
  v15 = 0;
  if ( !a9 )
  {
    v16 = g_hNetpEventLogHandle;
    if ( !g_hNetpEventLogHandle )
    {
      CreateNetpEventLogHandle(a1, a2, a3);
      v16 = g_hNetpEventLogHandle;
      goto LABEL_11;
    }
LABEL_12:
    if ( g_fEventSourceMsdtcCore
      && (ServiceNameFromTmInstance = GetServiceNameFromTmInstance(&v32), v10 = v32, ServiceNameFromTmInstance >= 0)
      && v32 )
    {
      v19 = -1;
      do
        ++v19;
      while ( v32[v19] );
      v20 = Src;
      v21 = 2 * v19;
      v22 = (unsigned int)Size;
      if ( Src )
        v23 = v21 + Size + 4;
      else
        v23 = 2 * v19;
      v24 = (char *)CoTaskMemAlloc(v23);
      if ( v24 )
      {
        v25 = v22;
        v15 = v24;
        LODWORD(v22) = v23;
        v9 = 0;
        if ( v20 )
        {
          v26 = v25;
          memcpy_0(v24, v20, v25);
          *(_DWORD *)&v24[v26] = 0;
          v24 += v26 + 4;
          v9 = 0;
        }
        memcpy_0(v24, v10, v21);
        v20 = v15;
      }
      else
      {
        v9 = 0;
      }
      v14 = a9;
    }
    else
    {
      v20 = Src;
      LODWORD(v22) = Size;
    }
    v27 = v31;
    v28 = NetpEventlogWriteEx3(v16, v29, v30, v31);
    if ( !v28 || v28 == 183 )
      goto LABEL_32;
    goto LABEL_31;
  }
  v16 = g_hNetpEventLog2Handle;
  if ( g_hNetpEventLog2Handle )
    goto LABEL_12;
  CreateNetpEventLog2Handle(a1, a2, a3);
  v16 = g_hNetpEventLog2Handle;
LABEL_11:
  if ( v16 )
    goto LABEL_12;
  v20 = Src;
  LODWORD(v22) = Size;
  v27 = v31;
LABEL_31:
  v9 = DtcWriteToEventLoggerExUnFilteredW(v29, v30, v27, v17, a5, v22, (const unsigned __int16 **)a7, v20, v14);
LABEL_32:
  CoTaskMemFree(v10);
  CoTaskMemFree(v15);
  return v9;
}

```

## disassembly

```asm
0x180070f24  mov     rax, rsp
0x180070f27  mov     [rax+20h], r9
0x180070f2b  mov     [rax+18h], r8d
0x180070f2f  mov     [rax+10h], dx
0x180070f33  mov     [rax+8], cx
0x180070f37  push    rbx
0x180070f38  push    rbp
0x180070f39  push    rsi
0x180070f3a  push    rdi
0x180070f3b  push    r12
0x180070f3d  push    r13
0x180070f3f  push    r14
0x180070f41  push    r15
0x180070f43  sub     rsp, 68h
0x180070f47  xor     ebx, ebx
0x180070f49  mov     [rax+20h], rbx
0x180070f4d  mov     r14d, ebx
0x180070f50  mov     eax, cs:?g_dwDuplicateEventFilterTimeout@@3KA; ulong g_dwDuplicateEventFilterTimeout
0x180070f56  cmp     eax, 0FFFFFFFFh
0x180070f59  jnz     short loc_180070F96
0x180070f5b  mov     edx, 5265C00h; unsigned int
0x180070f60  lea     rcx, aSuppressduplic; "SuppressDuplicateDuration"
0x180070f67  call    ?GetLocalDTCProfileInt@@YAKPEBDK@Z; GetLocalDTCProfileInt(char const *,ulong)
0x180070f6c  mov     r8d, [rsp+0A8h+arg_10]; unsigned int
0x180070f74  movzx   edx, [rsp+0A8h+arg_8]; unsigned __int16
0x180070f7c  movzx   ecx, [rsp+0A8h+arg_0]; unsigned __int16
0x180070f84  mov     cs:?g_dwDuplicateEventFilterTimeout@@3KA, eax; ulong g_dwDuplicateEventFilterTimeout
0x180070f8a  test    eax, eax
0x180070f8c  jnz     short loc_180070FE1
0x180070f8e  mov     eax, ebx
0x180070f90  mov     cs:?g_dwDuplicateEventFilterTimeout@@3KA, ebx; ulong g_dwDuplicateEventFilterTimeout
0x180070f96  test    eax, eax
0x180070f98  jnz     short loc_180070FE1
0x180070f9a  mov     eax, [rsp+0A8h+arg_40]
0x180070fa1  mov     [rsp+0A8h+var_68], eax; int
0x180070fa5  mov     rax, [rsp+0A8h+Src]
0x180070fad  mov     [rsp+0A8h+var_70], rax; void *
0x180070fb2  mov     rax, [rsp+0A8h+arg_30]
0x180070fba  mov     [rsp+0A8h+var_78], rax; unsigned __int16 **
0x180070fbf  mov     eax, dword ptr [rsp+0A8h+Size]
0x180070fc6  mov     [rsp+0A8h+var_80], eax; unsigned int
0x180070fca  movzx   eax, [rsp+0A8h+arg_20]
0x180070fd2  mov     [rsp+0A8h+var_88], ax; unsigned __int16
0x180070fd7  call    ?DtcWriteToEventLoggerExUnFilteredW@@YAJGGKPEAXGKPEAPEBG0H@Z; DtcWriteToEventLoggerExUnFilteredW(ushort,ushort,ulong,void *,ushort,ulong,ushort const * *,void *,int)
0x180070fdc  jmp     loc_1800711BB
0x180070fe1  mov     r15d, [rsp+0A8h+arg_40]
0x180070fe9  mov     r12, rbx
0x180070fec  test    r15d, r15d
0x180070fef  jnz     short loc_18007100B
0x180070ff1  mov     rdi, cs:?g_hNetpEventLogHandle@@3PEAXEA; void * g_hNetpEventLogHandle
0x180070ff8  test    rdi, rdi
0x180070ffb  jnz     short loc_18007102C
0x180070ffd  call    CreateNetpEventLogHandle
0x180071002  mov     rdi, cs:?g_hNetpEventLogHandle@@3PEAXEA; void * g_hNetpEventLogHandle
0x180071009  jmp     short loc_180071023
0x18007100b  mov     rdi, cs:?g_hNetpEventLog2Handle@@3PEAXEA; void * g_hNetpEventLog2Handle
0x180071012  test    rdi, rdi
0x180071015  jnz     short loc_18007102C
0x180071017  call    CreateNetpEventLog2Handle
0x18007101c  mov     rdi, cs:?g_hNetpEventLog2Handle@@3PEAXEA; void * g_hNetpEventLog2Handle
0x180071023  test    rdi, rdi
0x180071026  jz      loc_18007114E
0x18007102c  cmp     cs:?g_fEventSourceMsdtcCore@@3HA, ebx; int g_fEventSourceMsdtcCore
0x180071032  jz      loc_1800710E0
0x180071038  lea     rcx, [rsp+0A8h+arg_18]; unsigned __int16 **
0x180071040  call    ?GetServiceNameFromTmInstance@@YAJPEAPEAG@Z; GetServiceNameFromTmInstance(ushort * *)
0x180071045  mov     r14, [rsp+0A8h+arg_18]
0x18007104d  test    eax, eax
0x18007104f  js      loc_1800710E0
0x180071055  test    r14, r14
0x180071058  jz      loc_1800710E0
0x18007105e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180071062  inc     rax
0x180071065  cmp     [r14+rax*2], bx
0x18007106a  jnz     short loc_180071062
0x18007106c  mov     rsi, [rsp+0A8h+Src]
0x180071074  lea     r13d, [rax+rax]
0x180071078  mov     ebp, dword ptr [rsp+0A8h+Size]
0x18007107f  test    rsi, rsi
0x180071082  jz      short loc_18007108C
0x180071084  lea     ebx, [rbp+4]
0x180071087  add     ebx, r13d
0x18007108a  jmp     short loc_18007108F
0x18007108c  mov     ebx, r13d
0x18007108f  mov     ecx, ebx; cb
0x180071091  call    cs:__imp_CoTaskMemAlloc
0x180071097  mov     r15, rax
0x18007109a  test    rax, rax
0x18007109d  jz      short loc_1800710F1
0x18007109f  mov     rax, rbp
0x1800710a2  mov     r12, r15
0x1800710a5  mov     ebp, ebx
0x1800710a7  xor     ebx, ebx
0x1800710a9  test    rsi, rsi
0x1800710ac  jz      short loc_1800710CD
0x1800710ae  mov     r8, rax; Size
0x1800710b1  mov     rdx, rsi; Src
0x1800710b4  mov     rcx, r15; void *
0x1800710b7  mov     rbx, rax
0x1800710ba  call    memcpy_0
0x1800710bf  lea     rax, [rbx+r15]
0x1800710c3  xor     ecx, ecx
0x1800710c5  mov     [rax], ecx
0x1800710c7  lea     r15, [rax+4]
0x1800710cb  xor     ebx, ebx
0x1800710cd  mov     r8d, r13d; Size
0x1800710d0  mov     rdx, r14; Src
0x1800710d3  mov     rcx, r15; void *
0x1800710d6  call    memcpy_0
0x1800710db  mov     rsi, r12
0x1800710de  jmp     short loc_1800710F3
0x1800710e0  mov     rsi, [rsp+0A8h+Src]
0x1800710e8  mov     ebp, dword ptr [rsp+0A8h+Size]
0x1800710ef  jmp     short loc_1800710FB
0x1800710f1  xor     ebx, ebx
0x1800710f3  mov     r15d, [rsp+0A8h+arg_40]
0x1800710fb  movzx   eax, [rsp+0A8h+arg_20]
0x180071103  mov     rcx, rdi
0x180071106  mov     r13d, [rsp+0A8h+arg_10]
0x18007110e  mov     r9d, r13d
0x180071111  movzx   r8d, [rsp+0A8h+arg_8]
0x18007111a  movzx   edx, [rsp+0A8h+arg_0]
0x180071122  mov     [rsp+0A8h+var_58], ebp
0x180071126  mov     [rsp+0A8h+var_60], rsi
0x18007112b  mov     [rsp+0A8h+var_68], eax
0x18007112f  mov     rax, [rsp+0A8h+arg_30]
0x180071137  mov     [rsp+0A8h+var_70], rax
0x18007113c  call    NetpEventlogWriteEx3
0x180071141  test    eax, eax
0x180071143  jz      short loc_1800711A7
0x180071145  cmp     eax, 0B7h
0x18007114a  jz      short loc_1800711A7
0x18007114c  jmp     short loc_180071165
0x18007114e  mov     rsi, [rsp+0A8h+Src]
0x180071156  mov     ebp, dword ptr [rsp+0A8h+Size]
0x18007115d  mov     r13d, [rsp+0A8h+arg_10]
0x180071165  mov     rax, [rsp+0A8h+arg_30]
0x18007116d  mov     r8d, r13d; unsigned int
0x180071170  movzx   edx, [rsp+0A8h+arg_8]; unsigned __int16
0x180071178  movzx   ecx, [rsp+0A8h+arg_0]; unsigned __int16
0x180071180  mov     [rsp+0A8h+var_68], r15d; int
0x180071185  mov     [rsp+0A8h+var_70], rsi; void *
0x18007118a  mov     [rsp+0A8h+var_78], rax; unsigned __int16 **
0x18007118f  movzx   eax, [rsp+0A8h+arg_20]
0x180071197  mov     [rsp+0A8h+var_80], ebp; unsigned int
0x18007119b  mov     [rsp+0A8h+var_88], ax; unsigned __int16
0x1800711a0  call    ?DtcWriteToEventLoggerExUnFilteredW@@YAJGGKPEAXGKPEAPEBG0H@Z; DtcWriteToEventLoggerExUnFilteredW(ushort,ushort,ulong,void *,ushort,ulong,ushort const * *,void *,int)
0x1800711a5  mov     ebx, eax
0x1800711a7  mov     rcx, r14; pv
0x1800711aa  call    cs:__imp_CoTaskMemFree
0x1800711b0  mov     rcx, r12; pv
0x1800711b3  call    cs:__imp_CoTaskMemFree
0x1800711b9  mov     eax, ebx
0x1800711bb  add     rsp, 68h
0x1800711bf  pop     r15
0x1800711c1  pop     r14
0x1800711c3  pop     r13
0x1800711c5  pop     r12
0x1800711c7  pop     rdi
0x1800711c8  pop     rsi
0x1800711c9  pop     rbp
0x1800711ca  pop     rbx
0x1800711cb  retn
```
