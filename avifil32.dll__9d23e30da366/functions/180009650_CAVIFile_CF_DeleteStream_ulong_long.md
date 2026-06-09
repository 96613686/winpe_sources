# CAVIFile::CF::DeleteStream(ulong,long)

- ea: `0x180009650`
- end: `0x180009742`
- name: `?DeleteStream@CF@CAVIFile@@UEAAJKJ@Z`
- size: `242`
- prototype: `__int64 __fastcall(CAVIFile::CF *__hidden this, unsigned int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180008c3c`
- `0x180009650`
- `0x18000c3b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000966f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000966f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800096b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800096e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800096b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800096e6`

## pseudocode

```c
__int64 __fastcall CAVIFile::CF::DeleteStream(CAVIFile::CF *this, int a2, int a3)
{
  __int64 v3; // rsi
  int v6; // r9d
  int v7; // edx
  __int64 v8; // rdi
  __int64 v10; // rbp
  __int64 v11; // rdx

  v3 = *((_QWORD *)this + 1);
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 1264));
  if ( a3 < 0 || (v6 = *(_DWORD *)(v3 + 104), a3 >= v6) || (v7 = -1, v8 = 0, v6 <= 0) )
  {
LABEL_9:
    if ( v3 != -1264 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 1264));
    return 2147762291LL;
  }
  else
  {
    while ( 1 )
    {
      if ( !a2 || *(_DWORD *)(*(_QWORD *)(v3 + 8 * v8 + 736) + 64LL) == a2 )
        ++v7;
      if ( v7 == a3 )
        break;
      v8 = (unsigned int)(v8 + 1);
      if ( (int)v8 >= v6 )
        goto LABEL_9;
    }
    v10 = *(_QWORD *)(v3 + 8LL * (int)v8 + 736);
    if ( !*(_DWORD *)(v10 + 1392) )
    {
      *(_DWORD *)(v3 + 104) = v6 + 1;
      *(_DWORD *)(v3 + 136) -= StringLenAsAnsi((LPCWCH)(v10 + 140)) + 96;
      while ( (int)v8 < *(_DWORD *)(v3 + 104) )
      {
        v11 = (int)v8;
        LODWORD(v8) = v8 + 1;
        *(_QWORD *)(v3 + 8 * v11 + 736) = *(_QWORD *)(v3 + 8 * v11 + 744);
      }
      CAVIStream::~CAVIStream((CAVIStream *)v10);
      operator delete((void *)v10);
    }
    if ( v3 != -1264 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 1264));
    return 2147762277LL;
  }
}

```

## disassembly

```asm
0x180009650  push    rbx
0x180009652  push    rbp
0x180009653  push    rsi
0x180009654  push    rdi
0x180009655  push    r14
0x180009657  sub     rsp, 20h
0x18000965b  mov     rsi, [rcx+8]
0x18000965f  mov     ebp, r8d
0x180009662  mov     r14d, edx
0x180009665  lea     rbx, [rsi+4F0h]
0x18000966c  mov     rcx, rbx; lpCriticalSection
0x18000966f  call    cs:__imp_EnterCriticalSection
0x180009675  test    ebp, ebp
0x180009677  js      short loc_1800096AC
0x180009679  mov     r9d, [rsi+68h]
0x18000967d  cmp     ebp, r9d
0x180009680  jge     short loc_1800096AC
0x180009682  or      edx, 0FFFFFFFFh
0x180009685  xor     edi, edi
0x180009687  test    r9d, r9d
0x18000968a  jle     short loc_1800096AC
0x18000968c  test    r14d, r14d
0x18000968f  jz      short loc_18000969F
0x180009691  mov     rcx, [rsi+rdi*8+2E0h]
0x180009699  cmp     [rcx+40h], r14d
0x18000969d  jnz     short loc_1800096A1
0x18000969f  inc     edx
0x1800096a1  cmp     edx, ebp
0x1800096a3  jz      short loc_1800096CA
0x1800096a5  inc     edi
0x1800096a7  cmp     edi, r9d
0x1800096aa  jl      short loc_18000968C
0x1800096ac  test    rbx, rbx
0x1800096af  jz      short loc_1800096BA
0x1800096b1  mov     rcx, rbx; lpCriticalSection
0x1800096b4  call    cs:__imp_LeaveCriticalSection
0x1800096ba  mov     eax, 80044073h
0x1800096bf  add     rsp, 20h
0x1800096c3  pop     r14
0x1800096c5  pop     rdi
0x1800096c6  pop     rsi
0x1800096c7  pop     rbp
0x1800096c8  pop     rbx
0x1800096c9  retn
0x1800096ca  movsxd  rax, edi
0x1800096cd  mov     rbp, [rsi+rax*8+2E0h]
0x1800096d5  cmp     dword ptr [rbp+570h], 0
0x1800096dc  jz      short loc_1800096F3
0x1800096de  test    rbx, rbx
0x1800096e1  jz      short loc_1800096EC
0x1800096e3  mov     rcx, rbx; lpCriticalSection
0x1800096e6  call    cs:__imp_LeaveCriticalSection
0x1800096ec  mov     eax, 80044065h
0x1800096f1  jmp     short loc_1800096BF
0x1800096f3  lea     eax, [r9+1]
0x1800096f7  lea     rcx, [rbp+8Ch]; lpWideCharStr
0x1800096fe  mov     [rsi+68h], eax
0x180009701  call    StringLenAsAnsi
0x180009706  add     eax, 60h ; '`'
0x180009709  sub     [rsi+88h], eax
0x18000970f  jmp     short loc_180009726
0x180009711  movsxd  rdx, edi
0x180009714  inc     edi
0x180009716  mov     rax, [rsi+rdx*8+2E8h]
0x18000971e  mov     [rsi+rdx*8+2E0h], rax
0x180009726  cmp     edi, [rsi+68h]
0x180009729  jl      short loc_180009711
0x18000972b  mov     rcx, rbp; this
0x18000972e  call    ??1CAVIStream@@QEAA@XZ; CAVIStream::~CAVIStream(void)
0x180009733  mov     edx, 580h; unsigned __int64
0x180009738  mov     rcx, rbp; void *
0x18000973b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009740  jmp     short loc_1800096DE
```
