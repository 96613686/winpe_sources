# Vpath::removeFile(void)

- ea: `0x180093d10`
- end: `0x180093f73`
- name: `?removeFile@Vpath@@QEAAPEAVVstatus@@XZ`
- size: `611`
- prototype: `struct Vstatus *__fastcall(Vpath *__hidden this)`
- caller_count: `11`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180014a8c`
- `0x180070340`
- `0x18007bb70`
- `0x180093ac0`
- `0x180093f80`
- `0x1800947d0`
- `0x18009aae0`
- `0x1800e0540`
- `0x1800e0b90`
- `0x1800e0c90`
- `0x1800e19c0`

## callees

- `0x180047a4c`
- `0x180083790`
- `0x1800838f0`
- `0x180093d10`
- `0x180095100`
- `0x180095144`
- `0x180096770`
- `0x1800b7a58`
- `0x1800b7b38`
- `0x1800b93d0`
- `0x1801503e0`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180093da9`
- `KERNEL32!GetFileAttributesW` at `0x180093da9`
- `KERNEL32!SetFileAttributesW` at `0x180093de6`
- `KERNEL32!SetFileAttributesW` at `0x180093e5b`
- `KERNEL32!SetFileAttributesW` at `0x180093de6`
- `KERNEL32!SetFileAttributesW` at `0x180093e5b`
- `KERNEL32!SetFileAttributesA` at `0x180093dee`
- `KERNEL32!SetFileAttributesA` at `0x180093e63`
- `KERNEL32!SetFileAttributesA` at `0x180093dee`
- `KERNEL32!SetFileAttributesA` at `0x180093e63`
- `KERNEL32!DeleteFileW` at `0x180093e19`
- `KERNEL32!DeleteFileW` at `0x180093e19`
- `KERNEL32!DeleteFileA` at `0x180093e21`
- `KERNEL32!DeleteFileA` at `0x180093e21`
- `KERNEL32!GetFileAttributesA` at `0x180093db1`
- `KERNEL32!GetFileAttributesA` at `0x180093db1`
- `KERNEL32!GetLastError` at `0x180093e73`
- `KERNEL32!GetLastError` at `0x180093e73`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180093f38`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180093f38`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180093ecf`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180093ecf`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct Vstatus *__fastcall Vpath::removeFile(Vpath *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  int v5; // ecx
  char FileAttributesW; // al
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  int v10; // ebx
  int v11; // ecx
  DWORD v12; // edx
  int i; // ebx
  int v14; // ecx
  BOOL v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  int v19; // ecx
  char *v20; // rbx
  DWORD LastError; // edi
  VgenericStatus *v22; // rax
  VgenericStatus *v23; // rbx
  int *v24; // rcx
  _QWORD v26[4]; // [rsp+38h] [rbp-D0h] BYREF
  _WORD v27[256]; // [rsp+58h] [rbp-B0h] BYREF
  LPCWSTR lpFileName; // [rsp+258h] [rbp+150h]
  int v29; // [rsp+260h] [rbp+158h]
  char v30; // [rsp+264h] [rbp+15Ch]
  char Buffer[24]; // [rsp+268h] [rbp+160h] BYREF

  v26[1] = -2;
  Vpath::ClearStat(this);
  lpFileName = v27;
  v29 = 512;
  v27[0] = 0;
  v30 = 0;
  sub_1800B7B38((VstackStrLCP *)v27);
  if ( byte_1802B0030 )
  {
    if ( (unsigned __int8)sub_180096770(v3, v2, v4) )
      v5 = *(_DWORD *)(qword_1802B00B0 + 4);
    else
      v5 = 0;
    if ( v5 == 2 )
      FileAttributesW = GetFileAttributesW(lpFileName);
    else
      FileAttributesW = GetFileAttributesA((LPCSTR)lpFileName);
    v10 = (FileAttributesW & 0x20) != 0 ? 0x60 : 0;
    if ( (unsigned __int8)sub_180096770(v8, v7, v9) )
      v11 = *(_DWORD *)(qword_1802B00B0 + 4);
    else
      v11 = 0;
    v12 = v10 + 32;
    if ( v11 == 2 )
      SetFileAttributesW(lpFileName, v12);
    else
      SetFileAttributesA((LPCSTR)lpFileName, v12);
  }
  for ( i = 0; ; i = 1 )
  {
    if ( (unsigned __int8)sub_180096770(v3, v2, v4) )
      v14 = *(_DWORD *)(qword_1802B00B0 + 4);
    else
      v14 = 0;
    if ( v14 == 2 )
      v15 = DeleteFileW(lpFileName);
    else
      v15 = DeleteFileA((LPCSTR)lpFileName);
    if ( v15 )
    {
      v23 = 0;
      goto LABEL_42;
    }
    if ( i )
      break;
    if ( (unsigned __int8)sub_180096770(v17, v16, v18) )
      v19 = *(_DWORD *)(qword_1802B00B0 + 4);
    else
      v19 = 0;
    if ( v19 == 2 )
      SetFileAttributesW(lpFileName, 0x80u);
    else
      SetFileAttributesA((LPCSTR)lpFileName, 0x80u);
  }
  v20 = *(char **)this;
  LastError = GetLastError();
  v26[0] = dword_1802AFD5C;
  _InterlockedIncrement(&dword_1802AFD50);
  sub_180047A4C(v20, (RWCString *)v26);
  sub_180095144(Buffer, 0x14u, 0xFFFFFFFFFFFFFFFFuLL, "%d");
  if ( dword_1802B0018 )
    v22 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
  else
    v22 = (VgenericStatus *)malloc(0x20u);
  v26[2] = v22;
  if ( v22 )
    v23 = VgenericStatus::VgenericStatus(v22, 0x20007u, LastError, v26[0], Buffer);
  else
    v23 = 0;
  v24 = (int *)(v26[0] - 12LL);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v26[0] - 12LL), 0xFFFFFFFF) == 1 && v24 != &dword_1802AFD50 )
  {
    if ( dword_1802B0018 )
      COWSAllocator::Free(v24);
    else
      free(v24);
  }
LABEL_42:
  VstackStrLCP::~VstackStrLCP((VstackStrLCP *)v27);
  return v23;
}

```

## disassembly

```asm
0x180093d10  mov     rax, rsp
0x180093d13  push    rbp
0x180093d14  lea     rbp, [rax-188h]
0x180093d1b  sub     rsp, 280h
0x180093d22  mov     [rsp+280h+var_248], 0FFFFFFFFFFFFFFFEh
0x180093d2b  mov     [rax+10h], rbx
0x180093d2f  mov     [rax+18h], rdi
0x180093d33  mov     rax, cs:__security_cookie
0x180093d3a  xor     rax, rsp
0x180093d3d  mov     [rbp+180h+var_8], rax
0x180093d44  mov     rdi, rcx
0x180093d47  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x180093d4c  lea     rax, [rsp+280h+var_230]
0x180093d51  mov     [rbp+180h+lpFileName], rax
0x180093d58  mov     [rbp+180h+var_28], 200h
0x180093d62  and     [rsp+280h+var_230], 0
0x180093d68  mov     [rbp+180h+var_24], 0
0x180093d6f  mov     rdx, rdi
0x180093d72  lea     rcx, [rsp+280h+var_230]; this
0x180093d77  call    sub_1800B7B38
0x180093d7c  nop
0x180093d7d  cmp     cs:byte_1802B0030, 0
0x180093d84  jz      short loc_180093DF4
0x180093d86  call    sub_180096770
0x180093d8b  test    al, al
0x180093d8d  jz      short loc_180093D9B
0x180093d8f  mov     rax, cs:qword_1802B00B0
0x180093d96  mov     ecx, [rax+4]
0x180093d99  jmp     short loc_180093D9D
0x180093d9b  xor     ecx, ecx
0x180093d9d  cmp     ecx, 2
0x180093da0  mov     rcx, [rbp+180h+lpFileName]; lpFileName
0x180093da7  jnz     short loc_180093DB1
0x180093da9  call    cs:GetFileAttributesW
0x180093daf  jmp     short loc_180093DB7
0x180093db1  call    cs:GetFileAttributesA
0x180093db7  and     al, 20h
0x180093db9  neg     al
0x180093dbb  sbb     ebx, ebx
0x180093dbd  and     ebx, 60h
0x180093dc0  call    sub_180096770
0x180093dc5  test    al, al
0x180093dc7  jz      short loc_180093DD5
0x180093dc9  mov     rax, cs:qword_1802B00B0
0x180093dd0  mov     ecx, [rax+4]
0x180093dd3  jmp     short loc_180093DD7
0x180093dd5  xor     ecx, ecx
0x180093dd7  lea     edx, [rbx+20h]; dwFileAttributes
0x180093dda  cmp     ecx, 2
0x180093ddd  mov     rcx, [rbp+180h+lpFileName]; lpFileName
0x180093de4  jnz     short loc_180093DEE
0x180093de6  call    cs:SetFileAttributesW
0x180093dec  jmp     short loc_180093DF4
0x180093dee  call    cs:SetFileAttributesA
0x180093df4  xor     ebx, ebx
0x180093df6  call    sub_180096770
0x180093dfb  test    al, al
0x180093dfd  jz      short loc_180093E0B
0x180093dff  mov     rax, cs:qword_1802B00B0
0x180093e06  mov     ecx, [rax+4]
0x180093e09  jmp     short loc_180093E0D
0x180093e0b  xor     ecx, ecx
0x180093e0d  cmp     ecx, 2
0x180093e10  mov     rcx, [rbp+180h+lpFileName]; lpFileName
0x180093e17  jnz     short loc_180093E21
0x180093e19  call    cs:DeleteFileW
0x180093e1f  jmp     short loc_180093E27
0x180093e21  call    cs:DeleteFileA
0x180093e27  test    eax, eax
0x180093e29  jnz     loc_180093F40
0x180093e2f  test    ebx, ebx
0x180093e31  jnz     short loc_180093E70
0x180093e33  call    sub_180096770
0x180093e38  test    al, al
0x180093e3a  jz      short loc_180093E48
0x180093e3c  mov     rax, cs:qword_1802B00B0
0x180093e43  mov     ecx, [rax+4]
0x180093e46  jmp     short loc_180093E4A
0x180093e48  xor     ecx, ecx
0x180093e4a  mov     edx, 80h; dwFileAttributes
0x180093e4f  cmp     ecx, 2
0x180093e52  mov     rcx, [rbp+180h+lpFileName]; lpFileName
0x180093e59  jnz     short loc_180093E63
0x180093e5b  call    cs:SetFileAttributesW
0x180093e61  jmp     short loc_180093E69
0x180093e63  call    cs:SetFileAttributesA
0x180093e69  mov     ebx, 1
0x180093e6e  jmp     short loc_180093DF6
0x180093e70  mov     rbx, [rdi]
0x180093e73  call    cs:GetLastError
0x180093e79  mov     edi, eax
0x180093e7b  lea     rax, dword_1802AFD5C
0x180093e82  mov     [rsp+280h+var_250], rax
0x180093e87  lock inc cs:dword_1802AFD50
0x180093e8e  lea     rdx, [rsp+280h+var_250]; this
0x180093e93  mov     rcx, rbx; char *
0x180093e96  call    sub_180047A4C
0x180093e9b  mov     dword ptr [rsp+280h+var_260], edi
0x180093e9f  lea     r9, aD_3; "%d"
0x180093ea6  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180093eaa  lea     edx, [r8+15h]; BufferCount
0x180093eae  lea     rcx, [rbp+180h+Buffer]; Buffer
0x180093eb5  call    sub_180095144
0x180093eba  mov     ecx, 20h ; ' '; unsigned __int64
0x180093ebf  cmp     cs:dword_1802B0018, 0
0x180093ec6  jz      short loc_180093ECF
0x180093ec8  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180093ecd  jmp     short loc_180093ED5
0x180093ecf  call    cs:malloc
0x180093ed5  mov     [rsp+280h+var_240], rax
0x180093eda  test    rax, rax
0x180093edd  jz      short loc_180093F05
0x180093edf  lea     rcx, [rbp+180h+Buffer]
0x180093ee6  mov     [rsp+280h+var_260], rcx
0x180093eeb  mov     r9, [rsp+280h+var_250]
0x180093ef0  mov     r8d, edi; int
0x180093ef3  mov     edx, 20007h; unsigned int
0x180093ef8  mov     rcx, rax; this
0x180093efb  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x180093f00  mov     rbx, rax
0x180093f03  jmp     short loc_180093F07
0x180093f05  xor     ebx, ebx
0x180093f07  mov     rcx, [rsp+280h+var_250]
0x180093f0c  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x180093f10  or      eax, 0FFFFFFFFh
0x180093f13  lock xadd [rcx], eax
0x180093f17  cmp     eax, 1
0x180093f1a  jnz     short loc_180093F42
0x180093f1c  lea     rax, dword_1802AFD50
0x180093f23  cmp     rcx, rax
0x180093f26  jz      short loc_180093F42
0x180093f28  cmp     cs:dword_1802B0018, 0
0x180093f2f  jz      short loc_180093F38
0x180093f31  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x180093f36  jmp     short loc_180093F42
0x180093f38  call    cs:free
0x180093f3e  jmp     short loc_180093F42
0x180093f40  xor     ebx, ebx
0x180093f42  lea     rcx, [rsp+280h+var_230]; this
0x180093f47  call    ??1VstackStrLCP@@QEAA@XZ_0; VstackStrLCP::~VstackStrLCP(void)
0x180093f4c  mov     rax, rbx
0x180093f4f  mov     rcx, [rbp+180h+var_8]
0x180093f56  xor     rcx, rsp
0x180093f59  call    sub_1801503E0
0x180093f5e  lea     r11, [rsp+280h+var_s0]
0x180093f66  mov     rbx, [r11+18h]
0x180093f6a  mov     rdi, [r11+20h]
0x180093f6e  mov     rsp, r11
0x180093f71  pop     rbp
0x180093f72  retn
```
