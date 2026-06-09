# DtcWriteToEventLoggerExW(ushort,ushort,ulong,void *,ushort,ulong,ushort const * *,void *,int)

- ea: `0x180013e24`
- end: `0x1800140cc`
- name: `?DtcWriteToEventLoggerExW@@YAJGGKPEAXGKPEAPEBG0H@Z`
- size: `680`
- prototype: `__int64 __fastcall(unsigned __int16, unsigned __int16, unsigned int, void *, unsigned __int16, size_t Size, const unsigned __int16 **, void *Src, int)`
- caller_count: `11`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006750`
- `0x180008e10`
- `0x180009370`
- `0x18000f8dc`
- `0x180010b40`
- `0x180013a84`
- `0x180013c10`
- `0x1800487b0`
- `0x1800490e0`
- `0x1800856d4`
- `0x180085fa4`

## callees

- `0x18000d090`
- `0x18000f370`
- `0x18001075c`
- `0x180013e24`
- `0x180025104`
- `0x1800854d4`
- `0x18008557c`
- `0x1800ad0dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800140aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800140b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800140aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800140b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013f91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013f91`

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
0x180013e24  mov     rax, rsp
0x180013e27  mov     [rax+20h], r9
0x180013e2b  mov     [rax+18h], r8d
0x180013e2f  mov     [rax+10h], dx
0x180013e33  mov     [rax+8], cx
0x180013e37  push    rbx
0x180013e38  push    rbp
0x180013e39  push    rsi
0x180013e3a  push    rdi
0x180013e3b  push    r12
0x180013e3d  push    r13
0x180013e3f  push    r14
0x180013e41  push    r15
0x180013e43  sub     rsp, 68h
0x180013e47  xor     ebx, ebx
0x180013e49  mov     [rax+20h], rbx
0x180013e4d  mov     r14d, ebx
0x180013e50  mov     eax, cs:?g_dwDuplicateEventFilterTimeout@@3KA; ulong g_dwDuplicateEventFilterTimeout
0x180013e56  cmp     eax, 0FFFFFFFFh
0x180013e59  jnz     short loc_180013E96
0x180013e5b  mov     edx, 5265C00h; unsigned int
0x180013e60  lea     rcx, aSuppressduplic; "SuppressDuplicateDuration"
0x180013e67  call    ?GetLocalDTCProfileInt@@YAKPEBDK@Z; GetLocalDTCProfileInt(char const *,ulong)
0x180013e6c  mov     r8d, [rsp+0A8h+arg_10]; unsigned int
0x180013e74  movzx   edx, [rsp+0A8h+arg_8]; unsigned __int16
0x180013e7c  movzx   ecx, [rsp+0A8h+arg_0]; unsigned __int16
0x180013e84  mov     cs:?g_dwDuplicateEventFilterTimeout@@3KA, eax; ulong g_dwDuplicateEventFilterTimeout
0x180013e8a  test    eax, eax
0x180013e8c  jnz     short loc_180013EE1
0x180013e8e  mov     eax, ebx
0x180013e90  mov     cs:?g_dwDuplicateEventFilterTimeout@@3KA, ebx; ulong g_dwDuplicateEventFilterTimeout
0x180013e96  test    eax, eax
0x180013e98  jnz     short loc_180013EE1
0x180013e9a  mov     eax, [rsp+0A8h+arg_40]
0x180013ea1  mov     [rsp+0A8h+var_68], eax; int
0x180013ea5  mov     rax, [rsp+0A8h+Src]
0x180013ead  mov     [rsp+0A8h+var_70], rax; void *
0x180013eb2  mov     rax, [rsp+0A8h+arg_30]
0x180013eba  mov     [rsp+0A8h+var_78], rax; unsigned __int16 **
0x180013ebf  mov     eax, dword ptr [rsp+0A8h+Size]
0x180013ec6  mov     [rsp+0A8h+var_80], eax; unsigned int
0x180013eca  movzx   eax, [rsp+0A8h+arg_20]
0x180013ed2  mov     [rsp+0A8h+var_88], ax; unsigned __int16
0x180013ed7  call    ?DtcWriteToEventLoggerExUnFilteredW@@YAJGGKPEAXGKPEAPEBG0H@Z; DtcWriteToEventLoggerExUnFilteredW(ushort,ushort,ulong,void *,ushort,ulong,ushort const * *,void *,int)
0x180013edc  jmp     loc_1800140BB
0x180013ee1  mov     r15d, [rsp+0A8h+arg_40]
0x180013ee9  mov     r12, rbx
0x180013eec  test    r15d, r15d
0x180013eef  jnz     short loc_180013F0B
0x180013ef1  mov     rdi, cs:?g_hNetpEventLogHandle@@3PEAXEA; void * g_hNetpEventLogHandle
0x180013ef8  test    rdi, rdi
0x180013efb  jnz     short loc_180013F2C
0x180013efd  call    CreateNetpEventLogHandle
0x180013f02  mov     rdi, cs:?g_hNetpEventLogHandle@@3PEAXEA; void * g_hNetpEventLogHandle
0x180013f09  jmp     short loc_180013F23
0x180013f0b  mov     rdi, cs:?g_hNetpEventLog2Handle@@3PEAXEA; void * g_hNetpEventLog2Handle
0x180013f12  test    rdi, rdi
0x180013f15  jnz     short loc_180013F2C
0x180013f17  call    CreateNetpEventLog2Handle
0x180013f1c  mov     rdi, cs:?g_hNetpEventLog2Handle@@3PEAXEA; void * g_hNetpEventLog2Handle
0x180013f23  test    rdi, rdi
0x180013f26  jz      loc_18001404E
0x180013f2c  cmp     cs:?g_fEventSourceMsdtcCore@@3HA, ebx; int g_fEventSourceMsdtcCore
0x180013f32  jz      loc_180013FE0
0x180013f38  lea     rcx, [rsp+0A8h+arg_18]; unsigned __int16 **
0x180013f40  call    ?GetServiceNameFromTmInstance@@YAJPEAPEAG@Z; GetServiceNameFromTmInstance(ushort * *)
0x180013f45  mov     r14, [rsp+0A8h+arg_18]
0x180013f4d  test    eax, eax
0x180013f4f  js      loc_180013FE0
0x180013f55  test    r14, r14
0x180013f58  jz      loc_180013FE0
0x180013f5e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013f62  inc     rax
0x180013f65  cmp     [r14+rax*2], bx
0x180013f6a  jnz     short loc_180013F62
0x180013f6c  mov     rsi, [rsp+0A8h+Src]
0x180013f74  lea     r13d, [rax+rax]
0x180013f78  mov     ebp, dword ptr [rsp+0A8h+Size]
0x180013f7f  test    rsi, rsi
0x180013f82  jz      short loc_180013F8C
0x180013f84  lea     ebx, [rbp+4]
0x180013f87  add     ebx, r13d
0x180013f8a  jmp     short loc_180013F8F
0x180013f8c  mov     ebx, r13d
0x180013f8f  mov     ecx, ebx; cb
0x180013f91  call    cs:__imp_CoTaskMemAlloc
0x180013f97  mov     r15, rax
0x180013f9a  test    rax, rax
0x180013f9d  jz      short loc_180013FF1
0x180013f9f  mov     rax, rbp
0x180013fa2  mov     r12, r15
0x180013fa5  mov     ebp, ebx
0x180013fa7  xor     ebx, ebx
0x180013fa9  test    rsi, rsi
0x180013fac  jz      short loc_180013FCD
0x180013fae  mov     r8, rax; Size
0x180013fb1  mov     rdx, rsi; Src
0x180013fb4  mov     rcx, r15; void *
0x180013fb7  mov     rbx, rax
0x180013fba  call    memcpy_0
0x180013fbf  lea     rax, [rbx+r15]
0x180013fc3  xor     ecx, ecx
0x180013fc5  mov     [rax], ecx
0x180013fc7  lea     r15, [rax+4]
0x180013fcb  xor     ebx, ebx
0x180013fcd  mov     r8d, r13d; Size
0x180013fd0  mov     rdx, r14; Src
0x180013fd3  mov     rcx, r15; void *
0x180013fd6  call    memcpy_0
0x180013fdb  mov     rsi, r12
0x180013fde  jmp     short loc_180013FF3
0x180013fe0  mov     rsi, [rsp+0A8h+Src]
0x180013fe8  mov     ebp, dword ptr [rsp+0A8h+Size]
0x180013fef  jmp     short loc_180013FFB
0x180013ff1  xor     ebx, ebx
0x180013ff3  mov     r15d, [rsp+0A8h+arg_40]
0x180013ffb  movzx   eax, [rsp+0A8h+arg_20]
0x180014003  mov     rcx, rdi
0x180014006  mov     r13d, [rsp+0A8h+arg_10]
0x18001400e  mov     r9d, r13d
0x180014011  movzx   r8d, [rsp+0A8h+arg_8]
0x18001401a  movzx   edx, [rsp+0A8h+arg_0]
0x180014022  mov     [rsp+0A8h+var_58], ebp
0x180014026  mov     [rsp+0A8h+var_60], rsi
0x18001402b  mov     [rsp+0A8h+var_68], eax
0x18001402f  mov     rax, [rsp+0A8h+arg_30]
0x180014037  mov     [rsp+0A8h+var_70], rax
0x18001403c  call    NetpEventlogWriteEx3
0x180014041  test    eax, eax
0x180014043  jz      short loc_1800140A7
0x180014045  cmp     eax, 0B7h
0x18001404a  jz      short loc_1800140A7
0x18001404c  jmp     short loc_180014065
0x18001404e  mov     rsi, [rsp+0A8h+Src]
0x180014056  mov     ebp, dword ptr [rsp+0A8h+Size]
0x18001405d  mov     r13d, [rsp+0A8h+arg_10]
0x180014065  mov     rax, [rsp+0A8h+arg_30]
0x18001406d  mov     r8d, r13d; unsigned int
0x180014070  movzx   edx, [rsp+0A8h+arg_8]; unsigned __int16
0x180014078  movzx   ecx, [rsp+0A8h+arg_0]; unsigned __int16
0x180014080  mov     [rsp+0A8h+var_68], r15d; int
0x180014085  mov     [rsp+0A8h+var_70], rsi; void *
0x18001408a  mov     [rsp+0A8h+var_78], rax; unsigned __int16 **
0x18001408f  movzx   eax, [rsp+0A8h+arg_20]
0x180014097  mov     [rsp+0A8h+var_80], ebp; unsigned int
0x18001409b  mov     [rsp+0A8h+var_88], ax; unsigned __int16
0x1800140a0  call    ?DtcWriteToEventLoggerExUnFilteredW@@YAJGGKPEAXGKPEAPEBG0H@Z; DtcWriteToEventLoggerExUnFilteredW(ushort,ushort,ulong,void *,ushort,ulong,ushort const * *,void *,int)
0x1800140a5  mov     ebx, eax
0x1800140a7  mov     rcx, r14; pv
0x1800140aa  call    cs:__imp_CoTaskMemFree
0x1800140b0  mov     rcx, r12; pv
0x1800140b3  call    cs:__imp_CoTaskMemFree
0x1800140b9  mov     eax, ebx
0x1800140bb  add     rsp, 68h
0x1800140bf  pop     r15
0x1800140c1  pop     r14
0x1800140c3  pop     r13
0x1800140c5  pop     r12
0x1800140c7  pop     rdi
0x1800140c8  pop     rsi
0x1800140c9  pop     rbp
0x1800140ca  pop     rbx
0x1800140cb  retn
```
