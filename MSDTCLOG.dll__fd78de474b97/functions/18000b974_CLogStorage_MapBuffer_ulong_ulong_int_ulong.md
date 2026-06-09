# CLogStorage::_MapBuffer(ulong,ulong,int,ulong)

- ea: `0x18000b974`
- end: `0x18000bc3b`
- name: `?_MapBuffer@CLogStorage@@AEAAPEAVCBuffer@@KKHK@Z`
- size: `711`
- prototype: `struct CBuffer *(CLogStorage *__hidden this, unsigned int, unsigned int, int, unsigned int)`
- caller_count: `12`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002900`
- `0x18000a1a8`
- `0x18000a288`
- `0x18000aae4`
- `0x18000b06c`
- `0x18000b2c8`
- `0x18000b658`
- `0x18000b798`
- `0x18000bc44`
- `0x18000cec8`
- `0x18000d2f0`
- `0x18000d3ec`

## callees

- `0x180005ca8`
- `0x18000b974`
- `0x18000d998`
- `0x18001266c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000bc19`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000bc19`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000b9ce`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000b9ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9de`

## string_xrefs

- `0x18000b9ec`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000bac8`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000bb32`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000bbe9`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct CBuffer *__fastcall CLogStorage::_MapBuffer(
        CLogStorage *this,
        unsigned int a2,
        unsigned int a3,
        int a4,
        unsigned int a5)
{
  DWORD v9; // r9d
  SIZE_T dwNumberOfBytesToMap; // rax
  char *v11; // rbp
  CBuffer *v12; // rsi
  DWORD LastError; // ebx
  int v14; // esi
  char *v15; // rdi
  unsigned int v16; // r8d
  unsigned int v17; // r11d
  unsigned int v18; // r9d
  __int64 v19; // r10
  bool v20; // zf
  int v21; // edx
  int v22; // ecx
  unsigned int v23; // eax
  unsigned int v24; // edx
  unsigned int *v25; // r9
  ulong pExceptionObject; // [rsp+88h] [rbp+10h] BYREF

  v9 = a2 & -*((_DWORD *)this + 11);
  dwNumberOfBytesToMap = *((_DWORD *)this + 8) - v9;
  if ( a2 + a3 <= *((_DWORD *)this + 8) )
    dwNumberOfBytesToMap = a3 + a2 - v9;
  v11 = (char *)MapViewOfFile(*((HANDLE *)this + 20), 2u, 0, v9, dwNumberOfBytesToMap);
  if ( v11 )
  {
    v14 = 1;
    v15 = (char *)this + 688;
    (**((void (__fastcall ***)(char *))this + 86))((char *)this + 688);
    v16 = *((_DWORD *)this + 187);
    v17 = *((_DWORD *)this + 186);
    if ( v17 >= v16 )
    {
      TraceFile(
        -2147430395,
        "IDS_DTC_W_LOGNOMORELOGBUFFERS",
        "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp",
        0x2E0u);
      LastError = -2147430395;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 8LL))(v15);
      goto LABEL_30;
    }
    if ( *((_DWORD *)this + 192) )
    {
      *(_QWORD *)((char *)this + 764) = 0;
      v18 = 0;
    }
    else if ( *((_DWORD *)this + 190) || *((_DWORD *)this + 191) != v16 - 1 )
    {
      v18 = ++*((_DWORD *)this + 191) % v16;
      *((_DWORD *)this + 191) = v18;
    }
    else
    {
      v18 = 0;
      v19 = 0;
      while ( 1 )
      {
        v20 = (_DWORD)v19 == v16;
        if ( (unsigned int)v19 >= v16 )
          break;
        v21 = *(_DWORD *)(*((_QWORD *)this + 94) + 80 * v19 + 68);
        v22 = v21 != 0 ? v14 : 0;
        v14 = v22;
        v23 = v19;
        if ( v21 )
          v23 = v18;
        v18 = v23;
        if ( v21 )
          v19 = (unsigned int)(v19 + 1);
        if ( !v22 )
        {
          v20 = (_DWORD)v19 == v16;
          break;
        }
      }
      if ( v20 )
      {
        TraceFile(
          -1073737670,
          "IDS_DTC_E_LOG_CORRUPT_ERROR",
          "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp",
          0x2C9u);
        LastError = -1073737670;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 8LL))(v15);
        goto LABEL_30;
      }
    }
    v12 = (CBuffer *)(*((_QWORD *)this + 94) + 80LL * v18);
    if ( !*((_DWORD *)v12 + 17) )
    {
      *((_DWORD *)this + 186) = v17 + 1;
      *((_DWORD *)v12 + 17) = 1;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 8LL))((char *)this + 688);
      v24 = a5;
      v25 = (unsigned int *)((char *)this + 40);
      if ( !a5 || a2 != *((_DWORD *)this + 8) - *v25 )
        v24 = *(_DWORD *)this;
      CBuffer::Init(v12, a2, a3, *v25, a4, v11, v24, *((_DWORD *)this + 11));
      return v12;
    }
    TraceFile(
      -1073737670,
      "IDS_DTC_E_LOG_CORRUPT_ERROR",
      "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp",
      0x2D7u);
    LastError = -1073737670;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 8LL))(v15);
LABEL_30:
    UnmapViewOfFile(v11);
    goto LABEL_31;
  }
  v12 = 0;
  LastError = GetLastError();
  TraceFile(LastError, "MapViewOfFile", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0x2A0u);
  if ( LastError )
  {
LABEL_31:
    pExceptionObject = LastError;
    throw &pExceptionObject;
  }
  return v12;
}

```

## disassembly

```asm
0x18000b974  mov     [rsp+arg_0], rbx
0x18000b979  mov     [rsp+arg_10], rbp
0x18000b97e  push    rsi
0x18000b97f  push    rdi
0x18000b980  push    r12
0x18000b982  push    r14
0x18000b984  push    r15
0x18000b986  sub     rsp, 50h
0x18000b98a  mov     r12d, r9d
0x18000b98d  mov     r15d, r8d
0x18000b990  mov     r14d, edx
0x18000b993  mov     rbx, rcx
0x18000b996  mov     r9d, [rcx+2Ch]
0x18000b99a  neg     r9d
0x18000b99d  and     r9d, edx; dwFileOffsetLow
0x18000b9a0  lea     r11d, [rdx+r8]
0x18000b9a4  mov     r10d, edx
0x18000b9a7  sub     r10d, r9d
0x18000b9aa  add     r10d, r8d
0x18000b9ad  mov     eax, [rcx+20h]
0x18000b9b0  sub     eax, r9d
0x18000b9b3  cmp     r11d, [rcx+20h]
0x18000b9b7  cmovbe  eax, r10d
0x18000b9bb  mov     [rsp+78h+dwNumberOfBytesToMap], rax; dwNumberOfBytesToMap
0x18000b9c0  xor     r8d, r8d; dwFileOffsetHigh
0x18000b9c3  lea     edx, [r8+2]; dwDesiredAccess
0x18000b9c7  mov     rcx, [rcx+0A0h]; hFileMappingObject
0x18000b9ce  call    cs:__imp_MapViewOfFile
0x18000b9d4  mov     rbp, rax
0x18000b9d7  test    rax, rax
0x18000b9da  jnz     short loc_18000BA0E
0x18000b9dc  xor     esi, esi
0x18000b9de  call    cs:__imp_GetLastError
0x18000b9e4  mov     ebx, eax
0x18000b9e6  mov     r9d, 2A0h; unsigned int
0x18000b9ec  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000b9f3  lea     rdx, aMapviewoffile; "MapViewOfFile"
0x18000b9fa  mov     ecx, eax; int
0x18000b9fc  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000ba01  test    ebx, ebx
0x18000ba03  jz      loc_18000BBC7
0x18000ba09  jmp     loc_18000BC1F
0x18000ba0e  mov     esi, 1
0x18000ba13  mov     [rsp+78h+var_38], esi
0x18000ba17  lea     rdi, [rbx+2B0h]
0x18000ba1e  mov     [rsp+78h+var_30], rdi
0x18000ba23  mov     rax, [rdi]
0x18000ba26  mov     rcx, rdi
0x18000ba29  mov     rax, [rax]
0x18000ba2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba31  nop
0x18000ba32  mov     r8d, [rbx+2ECh]
0x18000ba39  mov     r11d, [rbx+2E8h]
0x18000ba40  cmp     r11d, r8d
0x18000ba43  jnb     loc_18000BBE3
0x18000ba49  cmp     dword ptr [rbx+300h], 0
0x18000ba50  jz      short loc_18000BA65
0x18000ba52  mov     qword ptr [rbx+2FCh], 0
0x18000ba5d  xor     r9d, r9d
0x18000ba60  jmp     loc_18000BB14
0x18000ba65  cmp     dword ptr [rbx+2F8h], 0
0x18000ba6c  jnz     loc_18000BAFA
0x18000ba72  lea     eax, [r8-1]
0x18000ba76  cmp     [rbx+2FCh], eax
0x18000ba7c  jnz     short loc_18000BAFA
0x18000ba7e  xor     r9d, r9d
0x18000ba81  xor     r10d, r10d
0x18000ba84  cmp     r10d, r8d
0x18000ba87  jnb     short loc_18000BAC0
0x18000ba89  lea     rcx, [r10+r10*4]
0x18000ba8d  add     rcx, rcx
0x18000ba90  mov     rax, [rbx+2F0h]
0x18000ba97  mov     edx, [rax+rcx*8+44h]
0x18000ba9b  mov     eax, edx
0x18000ba9d  neg     eax
0x18000ba9f  sbb     ecx, ecx
0x18000baa1  and     ecx, esi
0x18000baa3  mov     esi, ecx
0x18000baa5  mov     eax, r10d
0x18000baa8  test    edx, edx
0x18000baaa  cmovnz  eax, r9d
0x18000baae  mov     r9d, eax
0x18000bab1  lea     eax, [r10+1]
0x18000bab5  cmovnz  r10d, eax
0x18000bab9  test    ecx, ecx
0x18000babb  jnz     short loc_18000BA84
0x18000babd  cmp     r10d, r8d
0x18000bac0  jnz     short loc_18000BB14
0x18000bac2  mov     r9d, 2C9h; unsigned int
0x18000bac8  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000bacf  lea     rdx, aIdsDtcELogCorr; "IDS_DTC_E_LOG_CORRUPT_ERROR"
0x18000bad6  mov     ecx, 0C000103Ah; int
0x18000badb  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000bae0  mov     ebx, 0C000103Ah
0x18000bae5  mov     rax, [rdi]
0x18000bae8  mov     rcx, rdi
0x18000baeb  mov     rax, [rax+8]
0x18000baef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baf4  nop
0x18000baf5  jmp     loc_18000BC16
0x18000bafa  add     [rbx+2FCh], esi
0x18000bb00  xor     edx, edx
0x18000bb02  mov     eax, [rbx+2FCh]
0x18000bb08  div     r8d
0x18000bb0b  mov     r9d, edx
0x18000bb0e  mov     [rbx+2FCh], edx
0x18000bb14  mov     eax, r9d
0x18000bb17  lea     rsi, [rax+rax*4]
0x18000bb1b  shl     rsi, 4
0x18000bb1f  add     rsi, [rbx+2F0h]
0x18000bb26  cmp     dword ptr [rsi+44h], 0
0x18000bb2a  jz      short loc_18000BB64
0x18000bb2c  mov     r9d, 2D7h; unsigned int
0x18000bb32  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000bb39  lea     rdx, aIdsDtcELogCorr; "IDS_DTC_E_LOG_CORRUPT_ERROR"
0x18000bb40  mov     ecx, 0C000103Ah; int
0x18000bb45  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000bb4a  mov     ebx, 0C000103Ah
0x18000bb4f  mov     rax, [rdi]
0x18000bb52  mov     rcx, rdi
0x18000bb55  mov     rax, [rax+8]
0x18000bb59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb5e  nop
0x18000bb5f  jmp     loc_18000BC16
0x18000bb64  lea     eax, [r11+1]
0x18000bb68  mov     [rbx+2E8h], eax
0x18000bb6e  mov     dword ptr [rsi+44h], 1
0x18000bb75  mov     rax, [rdi]
0x18000bb78  mov     rcx, rdi
0x18000bb7b  mov     rax, [rax+8]
0x18000bb7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb84  nop
0x18000bb85  mov     edx, [rsp+78h+arg_20]
0x18000bb8c  lea     r9, [rbx+28h]
0x18000bb90  test    edx, edx
0x18000bb92  jz      short loc_18000BB9F
0x18000bb94  mov     eax, [rbx+20h]
0x18000bb97  sub     eax, [r9]
0x18000bb9a  cmp     r14d, eax
0x18000bb9d  jz      short loc_18000BBA1
0x18000bb9f  mov     edx, [rbx]
0x18000bba1  mov     ecx, [rbx+2Ch]
0x18000bba4  mov     [rsp+78h+var_40], ecx; unsigned int
0x18000bba8  mov     [rsp+78h+var_48], edx; unsigned int
0x18000bbac  mov     [rsp+78h+var_50], rbp; pExceptionObject
0x18000bbb1  mov     dword ptr [rsp+78h+dwNumberOfBytesToMap], r12d; int
0x18000bbb6  mov     r9d, [r9]; unsigned int
0x18000bbb9  mov     r8d, r15d; unsigned int
0x18000bbbc  mov     edx, r14d; unsigned int
0x18000bbbf  mov     rcx, rsi; this
0x18000bbc2  call    ?Init@CBuffer@@QEAAXKKKHPEADKK@Z; CBuffer::Init(ulong,ulong,ulong,int,char *,ulong,ulong)
0x18000bbc7  mov     rax, rsi
0x18000bbca  lea     r11, [rsp+78h+var_28]
0x18000bbcf  mov     rbx, [r11+30h]
0x18000bbd3  mov     rbp, [r11+40h]
0x18000bbd7  mov     rsp, r11
0x18000bbda  pop     r15
0x18000bbdc  pop     r14
0x18000bbde  pop     r12
0x18000bbe0  pop     rdi
0x18000bbe1  pop     rsi
0x18000bbe2  retn
0x18000bbe3  mov     r9d, 2E0h; unsigned int
0x18000bbe9  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000bbf0  lea     rdx, aIdsDtcWLognomo; "IDS_DTC_W_LOGNOMORELOGBUFFERS"
0x18000bbf7  mov     ecx, 8000D005h; int
0x18000bbfc  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000bc01  mov     ebx, 8000D005h
0x18000bc06  mov     rax, [rdi]
0x18000bc09  mov     rcx, rdi
0x18000bc0c  mov     rax, [rax+8]
0x18000bc10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc15  nop
0x18000bc16  mov     rcx, rbp; lpBaseAddress
0x18000bc19  call    cs:__imp_UnmapViewOfFile
0x18000bc1f  mov     [rsp+78h+pExceptionObject], ebx
0x18000bc26  lea     rdx, _TI1K; pThrowInfo
0x18000bc2d  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000bc35  call    _CxxThrowException_0
```
