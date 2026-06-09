# CNLDP::GetSpellerShimDll(ushort,ResourceLoader6::ILoadResources *)

- ea: `0x180062ac4`
- end: `0x180062c44`
- name: `?GetSpellerShimDll@CNLDP@@QEAAPEAVCCsapi@@GPEAUILoadResources@ResourceLoader6@@@Z`
- size: `384`
- prototype: `struct CCsapi *(CNLDP *__hidden this, unsigned __int16, struct ResourceLoader6::ILoadResources *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180060470`

## callees

- `0x180002778`
- `0x180035640`
- `0x18003dfcc`
- `0x18003ed6c`
- `0x180062ac4`
- `0x180066238`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062b6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062c26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062b6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062c26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062af7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062af7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct CCsapi *__fastcall CNLDP::GetSpellerShimDll(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned __int16 a2,
        struct ResourceLoader6::ILoadResources *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r14
  int v7; // r9d
  unsigned __int64 v8; // r10
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  __int64 v10; // rbx
  struct CCsapi *v12; // rsi
  _WORD *v13; // rax
  _WORD *v14; // rbx
  __int64 OwningThread; // r9
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rdx
  _BYTE pExceptionObject[64]; // [rsp+30h] [rbp-58h] BYREF
  const void *retaddr; // [rsp+88h] [rbp+0h]

  v6 = this + 3;
  EnterCriticalSection(this + 3);
  v7 = 0;
  v8 = *(_QWORD *)&this[2].LockCount;
  v9 = this + 2;
  while ( v7 < (__int64)v8 )
  {
    if ( v7 >= v8 )
    {
      CNLException::CNLException((CNLException *)pExceptionObject, 2147942487LL, retaddr);
      throw (CNLException *)pExceptionObject;
    }
    _mm_lfence();
    if ( *(_WORD *)(*((_QWORD *)&this[2].DebugInfo->Type + v7) + 8LL) == a2 )
    {
      if ( (unsigned __int64)v7 >= *(_QWORD *)&this[2].LockCount )
      {
        CNLException::CNLException((CNLException *)pExceptionObject, 2147942487LL, retaddr);
        throw (CNLException *)pExceptionObject;
      }
      _mm_lfence();
      v10 = **((_QWORD **)&this[2].DebugInfo->Type + v7);
      LeaveCriticalSection(v6);
      return (struct CCsapi *)v10;
    }
    ++v7;
  }
  v12 = CCsapi::Create(a2, v7, a3);
  if ( v12 )
  {
    v13 = operator new(0x10u);
    v14 = v13;
    if ( v13 )
    {
      *(_QWORD *)v13 = v12;
      v13[4] = a2;
    }
    else
    {
      v14 = 0;
    }
    OwningThread = (__int64)v9->OwningThread;
    v16 = *(_QWORD *)&v9->LockCount;
    if ( v16 >= OwningThread )
    {
      v17 = *(_QWORD *)&v9->LockCount;
      if ( v16 < 8 )
        v17 = 8;
      v18 = OwningThread + v17;
      if ( v16 + 1 >= OwningThread + v17 )
        v18 = v16 + 1;
      if ( v18 > OwningThread )
      {
        CArray<NLG::ITrieIter *,CArrayAllocator_malloc>::ReallocWorker(v9);
        v16 = *(_QWORD *)&v9->LockCount;
      }
    }
    *((_QWORD *)&v9->DebugInfo->Type + v16) = v14;
    ++*(_QWORD *)&v9->LockCount;
  }
  LeaveCriticalSection(v6);
  return v12;
}

```

## disassembly

```asm
0x180062ac4  mov     r11, rsp
0x180062ac7  push    rsi
0x180062ac8  push    rdi
0x180062ac9  push    r14
0x180062acb  sub     rsp, 70h
0x180062acf  mov     qword ptr [r11-68h], 0FFFFFFFFFFFFFFFEh
0x180062ad7  mov     [r11+10h], rbx
0x180062adb  mov     [r11+18h], rbp
0x180062adf  mov     rsi, r8
0x180062ae2  movzx   ebp, dx
0x180062ae5  mov     rbx, rcx
0x180062ae8  lea     rax, [rcx+70h]
0x180062aec  mov     [r11-60h], rax
0x180062af0  lea     r14, [rax+8]
0x180062af4  mov     rcx, r14; lpCriticalSection
0x180062af7  call    cs:__imp_EnterCriticalSection
0x180062afd  nop
0x180062afe  xor     r9d, r9d; bool
0x180062b01  mov     r10, [rbx+58h]
0x180062b05  lea     rdi, [rbx+50h]
0x180062b09  movsxd  rdx, r9d; bool
0x180062b0c  cmp     rdx, r10
0x180062b0f  jge     loc_180062BA4
0x180062b15  jnb     short loc_180062B7B
0x180062b17  lfence
0x180062b1a  mov     rax, [rbx+50h]
0x180062b1e  mov     rcx, [rax+rdx*8]
0x180062b22  cmp     [rcx+8], bp
0x180062b26  jz      short loc_180062B2D
0x180062b28  inc     r9d
0x180062b2b  jmp     short loc_180062B09
0x180062b2d  cmp     rdx, [rbx+58h]
0x180062b31  jb      short loc_180062B5C
0x180062b33  mov     r8, [rsp+88h]; void *
0x180062b3b  mov     edx, 80070057h; int
0x180062b40  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180062b45  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180062b4a  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180062b51  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180062b56  call    _CxxThrowException_0
0x180062b5c  lfence
0x180062b5f  mov     rax, [rbx+50h]
0x180062b63  mov     rdx, [rax+rdx*8]
0x180062b67  mov     rbx, [rdx]
0x180062b6a  mov     rcx, r14; lpCriticalSection
0x180062b6d  call    cs:__imp_LeaveCriticalSection
0x180062b73  mov     rax, rbx
0x180062b76  jmp     loc_180062C2F
0x180062b7b  mov     r8, [rsp+88h]; void *
0x180062b83  mov     edx, 80070057h; int
0x180062b88  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180062b8d  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180062b92  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180062b99  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180062b9e  call    _CxxThrowException_0
0x180062ba4  mov     r8, rsi; struct ResourceLoader6::ILoadResources *
0x180062ba7  movzx   ecx, bp; unsigned __int16
0x180062baa  call    ?Create@CCsapi@@SAPEAV1@G_NPEAUILoadResources@ResourceLoader6@@0@Z; CCsapi::Create(ushort,bool,ResourceLoader6::ILoadResources *,bool)
0x180062baf  mov     rsi, rax
0x180062bb2  test    rax, rax
0x180062bb5  jz      short loc_180062C23
0x180062bb7  mov     ecx, 10h; Size
0x180062bbc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180062bc1  mov     rbx, rax
0x180062bc4  mov     [rsp+88h+arg_0], rax
0x180062bcc  test    rax, rax
0x180062bcf  jz      short loc_180062BDA
0x180062bd1  mov     [rax], rsi
0x180062bd4  mov     [rax+8], bp
0x180062bd8  jmp     short loc_180062BDC
0x180062bda  xor     ebx, ebx
0x180062bdc  mov     r9, [rdi+10h]
0x180062be0  mov     r8, [rdi+8]
0x180062be4  cmp     r8, r9
0x180062be7  jl      short loc_180062C18
0x180062be9  lea     rcx, [r8+1]
0x180062bed  mov     rax, r8
0x180062bf0  mov     edx, 8
0x180062bf5  cmp     r8, rdx
0x180062bf8  cmovl   rax, rdx
0x180062bfc  lea     rdx, [r9+rax]
0x180062c00  cmp     rcx, rdx
0x180062c03  cmovge  rdx, rcx
0x180062c07  cmp     rdx, r9
0x180062c0a  jle     short loc_180062C18
0x180062c0c  mov     rcx, rdi
0x180062c0f  call    ?ReallocWorker@?$CArray@PEAVITrieIter@NLG@@VCArrayAllocator_malloc@@@@AEAAX_J@Z; CArray<NLG::ITrieIter *,CArrayAllocator_malloc>::ReallocWorker(__int64)
0x180062c14  mov     r8, [rdi+8]
0x180062c18  mov     rax, [rdi]
0x180062c1b  mov     [rax+r8*8], rbx
0x180062c1f  inc     qword ptr [rdi+8]
0x180062c23  mov     rcx, r14; lpCriticalSection
0x180062c26  call    cs:__imp_LeaveCriticalSection
0x180062c2c  mov     rax, rsi
0x180062c2f  lea     r11, [rsp+88h+var_18]
0x180062c34  mov     rbx, [r11+28h]
0x180062c38  mov     rbp, [r11+30h]
0x180062c3c  mov     rsp, r11
0x180062c3f  pop     r14
0x180062c41  pop     rdi
0x180062c42  pop     rsi
0x180062c43  retn
```
