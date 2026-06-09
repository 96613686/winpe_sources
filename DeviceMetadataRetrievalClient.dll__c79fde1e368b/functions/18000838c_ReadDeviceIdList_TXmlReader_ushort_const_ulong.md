# ReadDeviceIdList(TXmlReader *,ushort const *,ulong *)

- ea: `0x18000838c`
- end: `0x18000853d`
- name: `?ReadDeviceIdList@@YAPEAPEAGPEAVTXmlReader@@PEBGPEAK@Z`
- size: `433`
- prototype: `unsigned __int16 **__fastcall(struct TXmlReader *this, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000913c`
- `0x18000dabc`

## callees

- `0x180004e2c`
- `0x18000838c`
- `0x18000eed0`
- `0x1800108d8`
- `0x180010a84`
- `0x1800135cc`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800083ca`
- `KERNEL32!HeapAlloc` at `0x1800083ca`
- `KERNEL32!GetProcessHeap` at `0x1800083b9`
- `KERNEL32!GetProcessHeap` at `0x180008442`
- `KERNEL32!GetProcessHeap` at `0x1800084dd`
- `KERNEL32!GetProcessHeap` at `0x1800084ff`
- `KERNEL32!GetProcessHeap` at `0x1800083b9`
- `KERNEL32!GetProcessHeap` at `0x180008442`
- `KERNEL32!GetProcessHeap` at `0x1800084dd`
- `KERNEL32!GetProcessHeap` at `0x1800084ff`
- `KERNEL32!SetLastError` at `0x18000851f`
- `KERNEL32!SetLastError` at `0x18000851f`
- `KERNEL32!HeapFree` at `0x1800084eb`
- `KERNEL32!HeapFree` at `0x18000850d`
- `KERNEL32!HeapFree` at `0x1800084eb`
- `KERNEL32!HeapFree` at `0x18000850d`
- `KERNEL32!HeapReAlloc` at `0x180008453`
- `KERNEL32!HeapReAlloc` at `0x180008453`

## string_xrefs

- `0x1800083e8`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000840a`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`

## pseudocode

```c
unsigned __int16 **__fastcall ReadDeviceIdList(struct TXmlReader *this, const unsigned __int16 *a2, unsigned int *a3)
{
  TXmlReader *v5; // rbx
  __int64 v6; // rbp
  HANDLE ProcessHeap; // rax
  void *v8; // rsi
  DWORD v9; // edi
  unsigned int v10; // r14d
  int ElementString; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned __int16 v14; // bx
  unsigned __int16 *v15; // r15
  HANDLE v16; // rax
  LPVOID v17; // rax
  unsigned __int16 *v18; // rax
  __int64 i; // rbx
  void *v20; // r15
  HANDLE v21; // rax
  HANDLE v22; // rax
  unsigned __int16 *v25; // [rsp+70h] [rbp+18h] BYREF

  v25 = 0;
  v5 = this;
  v6 = 0;
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 0, 0x320u);
  if ( v8 )
  {
    v9 = 0;
    v10 = 100;
    while ( !(unsigned int)TXmlReader::IsNodeQName(
                             v5,
                             a2,
                             L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/") )
    {
      ElementString = TXmlReader::ReadElementString(
                        v5,
                        a2,
                        L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/",
                        (const unsigned __int16 **)&v25);
      v14 = ElementString;
      if ( ElementString )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, a2);
        v9 = v14;
        break;
      }
      v15 = v25;
      if ( !v25 )
      {
        v9 = 13;
        break;
      }
      if ( (unsigned int)v6 <= v10 )
      {
        if ( (_DWORD)v6 == v10 )
        {
          v10 += 100;
          v16 = GetProcessHeap();
          v17 = HeapReAlloc(v16, 0, v8, 8LL * v10);
          if ( !v17 )
            goto LABEL_2;
          v8 = v17;
        }
      }
      else
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v13, v12);
      }
      v18 = MemMallocAndCopy(v15);
      *((_QWORD *)v8 + v6) = v18;
      if ( !v18 )
        goto LABEL_2;
      v5 = this;
      v6 = (unsigned int)(v6 + 1);
    }
  }
  else
  {
LABEL_2:
    v9 = 8;
  }
  *a3 = v6;
  if ( v9 )
  {
    if ( v8 )
    {
      for ( i = 0; (unsigned int)i < (unsigned int)v6; i = (unsigned int)(i + 1) )
      {
        v20 = (void *)*((_QWORD *)v8 + i);
        if ( v20 )
        {
          v21 = GetProcessHeap();
          HeapFree(v21, 0, v20);
          *((_QWORD *)v8 + i) = 0;
        }
      }
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v8);
      v8 = 0;
    }
    *a3 = 0;
  }
  SetLastError(v9);
  return (unsigned __int16 **)v8;
}

```

## disassembly

```asm
0x18000838c  mov     [rsp+arg_8], rbx
0x180008391  mov     [rsp+arg_0], rcx
0x180008396  push    rbp
0x180008397  push    rsi
0x180008398  push    rdi
0x180008399  push    r12
0x18000839b  push    r13
0x18000839d  push    r14
0x18000839f  push    r15
0x1800083a1  sub     rsp, 20h
0x1800083a5  mov     r13, r8
0x1800083a8  mov     [rsp+58h+arg_10], 0
0x1800083b1  mov     r12, rdx
0x1800083b4  mov     rbx, rcx
0x1800083b7  xor     ebp, ebp
0x1800083b9  call    cs:__imp_GetProcessHeap
0x1800083bf  xor     edx, edx; dwFlags
0x1800083c1  mov     r8d, 320h; dwBytes
0x1800083c7  mov     rcx, rax; hHeap
0x1800083ca  call    cs:__imp_HeapAlloc
0x1800083d0  mov     rsi, rax
0x1800083d3  test    rax, rax
0x1800083d6  jnz     short loc_1800083E2
0x1800083d8  mov     edi, 8
0x1800083dd  jmp     loc_1800084C1
0x1800083e2  xor     edi, edi
0x1800083e4  lea     r14d, [rdi+64h]
0x1800083e8  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/De"...
0x1800083ef  mov     rdx, r12; unsigned __int16 *
0x1800083f2  mov     rcx, rbx; this
0x1800083f5  call    ?IsNodeQName@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::IsNodeQName(ushort const *,ushort const *)
0x1800083fa  test    eax, eax
0x1800083fc  jnz     loc_1800084C1
0x180008402  lea     r9, [rsp+58h+arg_10]; unsigned __int16 **
0x180008407  mov     rdx, r12; unsigned __int16 *
0x18000840a  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/De"...
0x180008411  mov     rcx, rbx; this
0x180008414  call    ?ReadElementString@TXmlReader@@QEAAJPEBG0PEAPEBG@Z; TXmlReader::ReadElementString(ushort const *,ushort const *,ushort const * *)
0x180008419  mov     ebx, eax
0x18000841b  test    eax, eax
0x18000841d  jnz     short loc_18000848D
0x18000841f  mov     r15, [rsp+58h+arg_10]
0x180008424  test    r15, r15
0x180008427  jz      short loc_180008486
0x180008429  cmp     ebp, r14d
0x18000842c  jbe     short loc_180008435
0x18000842e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008433  jmp     short loc_180008465
0x180008435  jnz     short loc_180008465
0x180008437  add     r14d, 64h ; 'd'
0x18000843b  mov     ebx, r14d
0x18000843e  shl     rbx, 3
0x180008442  call    cs:__imp_GetProcessHeap
0x180008448  mov     r9, rbx; dwBytes
0x18000844b  mov     r8, rsi; lpMem
0x18000844e  mov     rcx, rax; hHeap
0x180008451  xor     edx, edx; dwFlags
0x180008453  call    cs:__imp_HeapReAlloc
0x180008459  test    rax, rax
0x18000845c  jz      loc_1800083D8
0x180008462  mov     rsi, rax
0x180008465  mov     rcx, r15; unsigned __int16 *
0x180008468  call    ?MemMallocAndCopy@@YAPEAGPEBG@Z; MemMallocAndCopy(ushort const *)
0x18000846d  mov     [rsi+rbp*8], rax
0x180008471  test    rax, rax
0x180008474  jz      loc_1800083D8
0x18000847a  mov     rbx, [rsp+58h+arg_0]
0x18000847f  inc     ebp
0x180008481  jmp     loc_1800083E8
0x180008486  mov     edi, 0Dh
0x18000848b  jmp     short loc_1800084C1
0x18000848d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008494  lea     rax, WPP_GLOBAL_Control
0x18000849b  cmp     rcx, rax
0x18000849e  jz      short loc_1800084BE
0x1800084a0  test    byte ptr [rcx+1Ch], 1
0x1800084a4  jz      short loc_1800084BE
0x1800084a6  mov     rcx, [rcx+10h]
0x1800084aa  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x1800084b1  mov     edx, 5Bh ; '['
0x1800084b6  mov     r9, r12
0x1800084b9  call    WPP_SF_S
0x1800084be  movzx   edi, bx
0x1800084c1  mov     [r13+0], ebp
0x1800084c5  test    edi, edi
0x1800084c7  jz      short loc_18000851D
0x1800084c9  test    rsi, rsi
0x1800084cc  jz      short loc_180008515
0x1800084ce  xor     ebx, ebx
0x1800084d0  test    ebp, ebp
0x1800084d2  jz      short loc_1800084FF
0x1800084d4  mov     r15, [rsi+rbx*8]
0x1800084d8  test    r15, r15
0x1800084db  jz      short loc_1800084F9
0x1800084dd  call    cs:__imp_GetProcessHeap
0x1800084e3  mov     r8, r15; lpMem
0x1800084e6  xor     edx, edx; dwFlags
0x1800084e8  mov     rcx, rax; hHeap
0x1800084eb  call    cs:__imp_HeapFree
0x1800084f1  mov     qword ptr [rsi+rbx*8], 0
0x1800084f9  inc     ebx
0x1800084fb  cmp     ebx, ebp
0x1800084fd  jb      short loc_1800084D4
0x1800084ff  call    cs:__imp_GetProcessHeap
0x180008505  mov     r8, rsi; lpMem
0x180008508  xor     edx, edx; dwFlags
0x18000850a  mov     rcx, rax; hHeap
0x18000850d  call    cs:__imp_HeapFree
0x180008513  xor     esi, esi
0x180008515  mov     dword ptr [r13+0], 0
0x18000851d  mov     ecx, edi; dwErrCode
0x18000851f  call    cs:__imp_SetLastError
0x180008525  mov     rbx, [rsp+58h+arg_8]
0x18000852a  mov     rax, rsi
0x18000852d  add     rsp, 20h
0x180008531  pop     r15
0x180008533  pop     r14
0x180008535  pop     r13
0x180008537  pop     r12
0x180008539  pop     rdi
0x18000853a  pop     rsi
0x18000853b  pop     rbp
0x18000853c  retn
```
