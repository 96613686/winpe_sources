# ServerCacheRead(_GUID *,ulong,ushort const *,int,ushort const *,CBuffer &)

- ea: `0x180005eac`
- end: `0x180005ffb`
- name: `?ServerCacheRead@@YAKPEAU_GUID@@KPEBGH1AEAVCBuffer@@@Z`
- size: `335`
- prototype: `__int64 __fastcall(struct _GUID *, int, const unsigned __int16 *, int, unsigned __int16 *, struct CBuffer *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180006d30`

## callees

- `0x180005090`
- `0x180005eac`
- `0x1800075d0`
- `0x1800136a0`
- `0x18002ab90`
- `0x18002b364`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f8f`

## pseudocode

```c
__int64 __fastcall ServerCacheRead(
        struct _GUID *a1,
        int a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int16 *a5,
        struct CBuffer *a6)
{
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rcx
  ulong v13; // edi
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  ulong v17; // [rsp+40h] [rbp-28h] BYREF
  LPVOID lpMem[4]; // [rsp+48h] [rbp-20h] BYREF
  unsigned int v19; // [rsp+88h] [rbp+20h] BYREF

  lpMem[0] = 0;
  v19 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v10, v11, (__int64)a3);
  }
  v13 = ScCacheRead(a4 == 0, (__int64)a1, a2, (__int64)a3, a4 == 0, a5, lpMem, &v19);
  if ( v13 )
    goto LABEL_6;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v14 = lpMem[0];
    CBuffer::Set(a6, (const unsigned __int8 *const)lpMem[0], v19);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &unsigned long `RTTI Type Descriptor', &v17) )
    {
      v19 = v17;
      v13 = v17;
      __eh34_try_continuation(0, &unsigned long `RTTI Type Descriptor', &loc_180005F77);
LABEL_6:
      v14 = lpMem[0];
    }
  }
  if ( v14 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v14);
  }
  WppTraceIndent(v12, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (int)&WPP_647da024c2503459d7fafff2f0112b72_Traceguids,
      (int)WPP_pszIndent,
      v13);
  }
  return v13;
}

```

## disassembly

```asm
0x180005eac  mov     rax, rsp
0x180005eaf  mov     [rax+8], rbx
0x180005eb3  mov     [rax+10h], rsi
0x180005eb7  push    rdi
0x180005eb8  push    r14
0x180005eba  push    r15
0x180005ebc  sub     rsp, 50h
0x180005ec0  mov     edi, r9d
0x180005ec3  mov     rbx, r8
0x180005ec6  mov     r14d, edx
0x180005ec9  mov     r15, rcx
0x180005ecc  mov     qword ptr [rax-20h], 0
0x180005ed4  mov     dword ptr [rax+20h], 0
0x180005edb  xor     edx, edx
0x180005edd  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180005ee2  lea     rsi, WPP_GLOBAL_Control
0x180005ee9  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ef0  cmp     rcx, rsi
0x180005ef3  jz      short loc_180005F14
0x180005ef5  test    byte ptr [rcx+1Ch], 2
0x180005ef9  jz      short loc_180005F14
0x180005efb  cmp     byte ptr [rcx+19h], 5
0x180005eff  jb      short loc_180005F14
0x180005f01  mov     edx, 0Fh
0x180005f06  mov     [rsp+68h+var_48], rbx
0x180005f0b  mov     rcx, [rcx+10h]
0x180005f0f  call    WPP_SF_sS
0x180005f14  xor     ecx, ecx
0x180005f16  test    edi, edi
0x180005f18  setz    cl
0x180005f1b  lea     rax, [rsp+68h+arg_18]
0x180005f23  mov     [rsp+68h+var_30], rax
0x180005f28  lea     rax, [rsp+68h+lpMem]
0x180005f2d  mov     [rsp+68h+var_38], rax
0x180005f32  mov     rax, [rsp+68h+arg_20]
0x180005f3a  mov     [rsp+68h+var_40], rax
0x180005f3f  mov     dword ptr [rsp+68h+var_48], ecx
0x180005f43  mov     r9, rbx
0x180005f46  mov     r8d, r14d
0x180005f49  mov     rdx, r15
0x180005f4c  call    ScCacheRead
0x180005f51  mov     edi, eax
0x180005f53  test    eax, eax
0x180005f55  jnz     short loc_180005F85
0x180005f57  mov     r8d, [rsp+68h+arg_18]; unsigned int
0x180005f5f  mov     rbx, [rsp+68h+lpMem]
0x180005f64  mov     rdx, rbx; unsigned __int8 *
0x180005f67  mov     rcx, [rsp+68h+arg_28]; this
0x180005f6f  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x180005f74  nop
0x180005f75  jmp     short loc_180005F8A
0x180005f77  lea     rsi, WPP_GLOBAL_Control
0x180005f7e  mov     edi, [rsp+68h+arg_18]
0x180005f85  mov     rbx, [rsp+68h+lpMem]
0x180005f8a  test    rbx, rbx
0x180005f8d  jz      short loc_180005FA3
0x180005f8f  call    cs:__imp_GetProcessHeap
0x180005f95  mov     rcx, rax; hHeap
0x180005f98  mov     r8, rbx; lpMem
0x180005f9b  xor     edx, edx; dwFlags
0x180005f9d  call    cs:__imp_HeapFree
0x180005fa3  mov     edx, 1
0x180005fa8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180005fad  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fb4  cmp     rcx, rsi
0x180005fb7  jz      short loc_180005FE5
0x180005fb9  test    byte ptr [rcx+1Ch], 2
0x180005fbd  jz      short loc_180005FE5
0x180005fbf  cmp     byte ptr [rcx+19h], 5
0x180005fc3  jb      short loc_180005FE5
0x180005fc5  mov     edx, 10h
0x180005fca  mov     dword ptr [rsp+68h+var_48], edi
0x180005fce  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180005fd5  lea     r8, WPP_647da024c2503459d7fafff2f0112b72_Traceguids
0x180005fdc  mov     rcx, [rcx+10h]
0x180005fe0  call    WPP_SF_sD
0x180005fe5  mov     eax, edi
0x180005fe7  mov     rbx, [rsp+68h+arg_0]
0x180005fec  mov     rsi, [rsp+68h+arg_8]
0x180005ff1  add     rsp, 50h
0x180005ff5  pop     r15
0x180005ff7  pop     r14
0x180005ff9  pop     rdi
0x180005ffa  retn
```
