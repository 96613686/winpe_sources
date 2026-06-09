# FormatMsgToBuffer(STRA *,_DEBUG_PRINTS *,char const *,ulong,char const *,char const *,char * *)

- ea: `0x180006ec8`
- end: `0x180007018`
- name: `?FormatMsgToBuffer@@YAXPEAVSTRA@@PEAU_DEBUG_PRINTS@@PEBDK22PEAPEAD@Z`
- size: `336`
- prototype: `void __usercall(struct STRA *this@<rcx>, struct _DEBUG_PRINTS *@<rdx>, const char *@<r8>, unsigned int@<r9d>, const char *, const char *, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007234`

## callees

- `0x180006ec8`
- `0x180007408`

## import_xrefs

- `msvcrt!strrchr` at `0x180006ee9`
- `msvcrt!strrchr` at `0x180006ee9`
- `msvcrt!_vsnprintf_s` at `0x180006f78`
- `msvcrt!_vsnprintf_s` at `0x180006fdb`
- `msvcrt!_vsnprintf_s` at `0x180006f78`
- `msvcrt!_vsnprintf_s` at `0x180006fdb`
- `msvcrt!strnlen` at `0x180007002`
- `msvcrt!strnlen` at `0x180007002`
- `msvcrt!sprintf_s` at `0x180006f40`
- `msvcrt!sprintf_s` at `0x180006f40`
- `KERNEL32!GetLastError` at `0x180006f98`
- `KERNEL32!GetLastError` at `0x180006f98`
- `KERNEL32!GetCurrentThreadId` at `0x180006eff`
- `KERNEL32!GetCurrentThreadId` at `0x180006eff`

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
  signed int LastError; // eax
  bool v18; // sf
  int v19; // eax
  const char *v20; // rcx

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
    if ( *((_DWORD *)this + 10) < 0x2800u && !BUFFER::ReallocStorage((BUFFER *)this, 0x2800u) )
    {
      LastError = GetLastError();
      v18 = LastError < 0;
      if ( LastError > 0 )
        v18 = 1;
      if ( v18 )
      {
        *this[4] = 0;
        v19 = 0;
        goto LABEL_18;
      }
    }
    if ( _vsnprintf_s(
           &this[4][v15],
           (unsigned int)(*((_DWORD *)this + 10) - v15),
           (unsigned int)(v16 + *((_DWORD *)this + 10)),
           Format,
           *a7) == -1 )
      this[4][*((_DWORD *)this + 10) - 1] = 0;
  }
  v20 = this[4];
  if ( v20 )
    v19 = strnlen(v20, *((unsigned int *)this + 10));
  else
    v19 = 0;
LABEL_18:
  *((_DWORD *)this + 12) = v19;
}

```

## disassembly

```asm
0x180006ec8  push    rbx
0x180006eca  push    rbp
0x180006ecb  push    rsi
0x180006ecc  push    rdi
0x180006ecd  push    r14
0x180006ecf  push    r15
0x180006ed1  sub     rsp, 48h
0x180006ed5  mov     rbp, rdx
0x180006ed8  mov     rbx, rcx
0x180006edb  mov     edx, 5Ch ; '\'; Ch
0x180006ee0  mov     rcx, r8; Str
0x180006ee3  mov     r14d, r9d
0x180006ee6  mov     rsi, r8
0x180006ee9  call    cs:__imp_strrchr
0x180006eef  mov     rdi, rax
0x180006ef2  test    rax, rax
0x180006ef5  jnz     short loc_180006EFC
0x180006ef7  mov     rdi, rsi
0x180006efa  jmp     short loc_180006EFF
0x180006efc  inc     rdi
0x180006eff  call    cs:__imp_GetCurrentThreadId
0x180006f05  mov     edx, [rbx+28h]; BufferCount
0x180006f08  lea     rcx, asc_18000CAB4; "??"
0x180006f0f  mov     [rsp+78h+var_40], r14d
0x180006f14  lea     r8, Format; "%lu %hs!%hs [%hs @ %d]:"
0x180006f1b  mov     [rsp+78h+var_48], rdi
0x180006f20  test    rbp, rbp
0x180006f23  mov     r9d, eax
0x180006f26  cmovz   rbp, rcx
0x180006f2a  mov     rcx, [rsp+78h+arg_20]
0x180006f32  mov     [rsp+78h+var_50], rcx
0x180006f37  mov     rcx, [rbx+20h]; Buffer
0x180006f3b  mov     [rsp+78h+ArgList], rbp
0x180006f40  call    cs:__imp_sprintf_s
0x180006f46  mov     edx, [rbx+28h]
0x180006f49  or      ebp, 0FFFFFFFFh
0x180006f4c  mov     rcx, [rbx+20h]
0x180006f50  mov     esi, ebp
0x180006f52  mov     r15, [rsp+78h+arg_30]
0x180006f5a  mov     r9, [rsp+78h+Format]; Format
0x180006f62  movsxd  rdi, eax
0x180006f65  sub     esi, edi
0x180006f67  add     rcx, rdi; Buffer
0x180006f6a  mov     rax, [r15]
0x180006f6d  mov     [rsp+78h+ArgList], rax; ArgList
0x180006f72  lea     r8d, [rsi+rdx]; MaxCount
0x180006f76  sub     edx, edi; BufferCount
0x180006f78  call    cs:__imp__vsnprintf_s
0x180006f7e  cmp     eax, ebp
0x180006f80  jnz     short loc_180006FF2
0x180006f82  mov     edx, 2800h; unsigned int
0x180006f87  cmp     [rbx+28h], edx
0x180006f8a  jnb     short loc_180006FB9
0x180006f8c  mov     rcx, rbx; this
0x180006f8f  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x180006f94  test    al, al
0x180006f96  jnz     short loc_180006FB9
0x180006f98  call    cs:__imp_GetLastError
0x180006f9e  test    eax, eax
0x180006fa0  jle     short loc_180006FAC
0x180006fa2  movzx   eax, ax
0x180006fa5  or      eax, 80070000h
0x180006faa  test    eax, eax
0x180006fac  jns     short loc_180006FB9
0x180006fae  mov     rax, [rbx+20h]
0x180006fb2  mov     byte ptr [rax], 0
0x180006fb5  xor     eax, eax
0x180006fb7  jmp     short loc_180007008
0x180006fb9  mov     ecx, [rbx+28h]
0x180006fbc  mov     rax, [r15]
0x180006fbf  mov     r9, [rsp+78h+Format]; Format
0x180006fc7  mov     [rsp+78h+ArgList], rax; ArgList
0x180006fcc  lea     r8d, [rsi+rcx]; MaxCount
0x180006fd0  sub     ecx, edi
0x180006fd2  mov     edx, ecx; BufferCount
0x180006fd4  mov     rcx, [rbx+20h]
0x180006fd8  add     rcx, rdi; Buffer
0x180006fdb  call    cs:__imp__vsnprintf_s
0x180006fe1  cmp     eax, ebp
0x180006fe3  jnz     short loc_180006FF2
0x180006fe5  mov     ecx, [rbx+28h]
0x180006fe8  mov     rax, [rbx+20h]
0x180006fec  dec     ecx
0x180006fee  mov     byte ptr [rcx+rax], 0
0x180006ff2  mov     rcx, [rbx+20h]; String
0x180006ff6  test    rcx, rcx
0x180006ff9  jnz     short loc_180006FFF
0x180006ffb  xor     eax, eax
0x180006ffd  jmp     short loc_180007008
0x180006fff  mov     edx, [rbx+28h]; MaxCount
0x180007002  call    cs:__imp_strnlen
0x180007008  mov     [rbx+30h], eax
0x18000700b  add     rsp, 48h
0x18000700f  pop     r15
0x180007011  pop     r14
0x180007013  pop     rdi
0x180007014  pop     rsi
0x180007015  pop     rbp
0x180007016  pop     rbx
0x180007017  retn
```
