# FormatMsgToBuffer(STRA *,_DEBUG_PRINTS *,char const *,ulong,char const *,char const *,char * *)

- ea: `0x180033ed4`
- end: `0x180033ffd`
- name: `?FormatMsgToBuffer@@YAXPEAVSTRA@@PEAU_DEBUG_PRINTS@@PEBDK22PEAPEAD@Z`
- size: `297`
- prototype: `void __usercall(struct STRA *this@<rcx>, struct _DEBUG_PRINTS *@<rdx>, const char *@<r8>, unsigned int@<r9d>, const char *, const char *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180034218`
- `0x1800342f4`

## callees

- `0x180004560`
- `0x180004a40`
- `0x180033ed4`

## import_xrefs

- `msvcrt!strrchr` at `0x180033ef5`
- `msvcrt!strrchr` at `0x180033ef5`
- `msvcrt!_vsnprintf_s` at `0x180033f84`
- `msvcrt!_vsnprintf_s` at `0x180033fd1`
- `msvcrt!_vsnprintf_s` at `0x180033f84`
- `msvcrt!_vsnprintf_s` at `0x180033fd1`
- `msvcrt!sprintf_s` at `0x180033f4c`
- `msvcrt!sprintf_s` at `0x180033f4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033f0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033f0b`

## pseudocode

```c
void __fastcall FormatMsgToBuffer(
        char **this,
        struct _DEBUG_PRINTS *a2,
        const char *a3,
        int a4,
        const char *a5,
        char *Format,
        char **a7)
{
  char *v11; // rax
  const char *v12; // rdi
  DWORD CurrentThreadId; // eax
  int v14; // eax
  __int64 v15; // rdi
  int v16; // esi

  v11 = strrchr(a3, 92);
  if ( v11 )
    v12 = v11 + 1;
  else
    v12 = a3;
  CurrentThreadId = GetCurrentThreadId();
  if ( !a2 )
    a2 = (struct _DEBUG_PRINTS *)"??";
  v14 = sprintf_s(this[4], *((unsigned int *)this + 10), "%lu %hs!%hs [%hs @ %d]:", CurrentThreadId, a2, a5, v12, a4);
  v15 = v14;
  v16 = -1 - v14;
  if ( _vsnprintf_s(
         &this[4][v14],
         (unsigned int)(*((_DWORD *)this + 10) - v14),
         (unsigned int)(-1 - v14 + *((_DWORD *)this + 10)),
         Format,
         *a7) == -1 )
  {
    if ( (int)STRA::Resize((STRA *)this, 0x2800u) < 0 )
    {
      *this[4] = 0;
      *((_DWORD *)this + 12) = 0;
      return;
    }
    if ( _vsnprintf_s(
           &this[4][v15],
           (unsigned int)(*((_DWORD *)this + 10) - v15),
           (unsigned int)(v16 + *((_DWORD *)this + 10)),
           Format,
           *a7) == -1 )
      this[4][*((_DWORD *)this + 10) - 1] = 0;
  }
  STRA::SyncWithBuffer((STRA *)this);
}

```

## disassembly

```asm
0x180033ed4  push    rbx
0x180033ed6  push    rbp
0x180033ed7  push    rsi
0x180033ed8  push    rdi
0x180033ed9  push    r14
0x180033edb  push    r15
0x180033edd  sub     rsp, 48h
0x180033ee1  mov     rbp, rdx
0x180033ee4  mov     rbx, rcx
0x180033ee7  mov     edx, 5Ch ; '\'; Ch
0x180033eec  mov     rcx, r8; Str
0x180033eef  mov     r14d, r9d
0x180033ef2  mov     rsi, r8
0x180033ef5  call    cs:__imp_strrchr
0x180033efb  mov     rdi, rax
0x180033efe  test    rax, rax
0x180033f01  jnz     short loc_180033F08
0x180033f03  mov     rdi, rsi
0x180033f06  jmp     short loc_180033F0B
0x180033f08  inc     rdi
0x180033f0b  call    cs:__imp_GetCurrentThreadId
0x180033f11  mov     edx, [rbx+28h]; BufferCount
0x180033f14  lea     rcx, asc_18004F154; "??"
0x180033f1b  mov     [rsp+78h+var_40], r14d
0x180033f20  lea     r8, aLuHsHsHsD; "%lu %hs!%hs [%hs @ %d]:"
0x180033f27  mov     [rsp+78h+var_48], rdi
0x180033f2c  test    rbp, rbp
0x180033f2f  mov     r9d, eax
0x180033f32  cmovz   rbp, rcx
0x180033f36  mov     rcx, [rsp+78h+arg_20]
0x180033f3e  mov     [rsp+78h+var_50], rcx
0x180033f43  mov     rcx, [rbx+20h]; Buffer
0x180033f47  mov     [rsp+78h+ArgList], rbp
0x180033f4c  call    cs:__imp_sprintf_s
0x180033f52  mov     edx, [rbx+28h]
0x180033f55  or      ebp, 0FFFFFFFFh
0x180033f58  mov     rcx, [rbx+20h]
0x180033f5c  mov     esi, ebp
0x180033f5e  mov     r15, [rsp+78h+arg_30]
0x180033f66  mov     r9, [rsp+78h+Format]; Format
0x180033f6e  movsxd  rdi, eax
0x180033f71  sub     esi, edi
0x180033f73  add     rcx, rdi; Buffer
0x180033f76  mov     rax, [r15]
0x180033f79  mov     [rsp+78h+ArgList], rax; ArgList
0x180033f7e  lea     r8d, [rsi+rdx]; MaxCount
0x180033f82  sub     edx, edi; BufferCount
0x180033f84  call    cs:__imp__vsnprintf_s
0x180033f8a  cmp     eax, ebp
0x180033f8c  jnz     short loc_180033FE8
0x180033f8e  mov     edx, 2800h; unsigned int
0x180033f93  mov     rcx, rbx; this
0x180033f96  call    ?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x180033f9b  test    eax, eax
0x180033f9d  jns     short loc_180033FAF
0x180033f9f  mov     rax, [rbx+20h]
0x180033fa3  mov     byte ptr [rax], 0
0x180033fa6  mov     dword ptr [rbx+30h], 0
0x180033fad  jmp     short loc_180033FF0
0x180033faf  mov     ecx, [rbx+28h]
0x180033fb2  mov     rax, [r15]
0x180033fb5  mov     r9, [rsp+78h+Format]; Format
0x180033fbd  mov     [rsp+78h+ArgList], rax; ArgList
0x180033fc2  lea     r8d, [rsi+rcx]; MaxCount
0x180033fc6  sub     ecx, edi
0x180033fc8  mov     edx, ecx; BufferCount
0x180033fca  mov     rcx, [rbx+20h]
0x180033fce  add     rcx, rdi; Buffer
0x180033fd1  call    cs:__imp__vsnprintf_s
0x180033fd7  cmp     eax, ebp
0x180033fd9  jnz     short loc_180033FE8
0x180033fdb  mov     ecx, [rbx+28h]
0x180033fde  mov     rax, [rbx+20h]
0x180033fe2  dec     ecx
0x180033fe4  mov     byte ptr [rcx+rax], 0
0x180033fe8  mov     rcx, rbx; this
0x180033feb  call    ?SyncWithBuffer@STRA@@QEAAXXZ; STRA::SyncWithBuffer(void)
0x180033ff0  add     rsp, 48h
0x180033ff4  pop     r15
0x180033ff6  pop     r14
0x180033ff8  pop     rdi
0x180033ff9  pop     rsi
0x180033ffa  pop     rbp
0x180033ffb  pop     rbx
0x180033ffc  retn
```
