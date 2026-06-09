# __EHM_AddPrefixToDebugMsg(ushort *,unsigned __int64,unsigned __int64 *,ushort const *,char *)

- ea: `0x14000404c`
- end: `0x14000421b`
- name: `?__EHM_AddPrefixToDebugMsg@@YAJPEAG_KPEA_KPEBGPEAD@Z`
- size: `463`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int64 *, const unsigned __int16 *, va_list Args)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400036d8`
- `0x140003948`

## callees

- `0x140003de4`
- `0x14000404c`
- `0x14000ae60`

## import_xrefs

- `KERNEL32!GetLocalTime` at `0x14000409d`
- `KERNEL32!GetLocalTime` at `0x14000409d`
- `KERNEL32!QueryPerformanceCounter` at `0x1400040a7`
- `KERNEL32!QueryPerformanceCounter` at `0x1400040a7`
- `KERNEL32!GetCurrentThreadId` at `0x1400040bb`
- `KERNEL32!GetCurrentThreadId` at `0x1400040bb`
- `msvcrt!_vsnwprintf` at `0x14000419c`
- `msvcrt!_vsnwprintf` at `0x14000419c`

## pseudocode

```c
__int64 __fastcall __EHM_AddPrefixToDebugMsg(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        const unsigned __int16 *a4,
        va_list Args)
{
  unsigned int v7; // edx
  unsigned __int64 v8; // rdi
  wchar_t *v9; // rsi
  unsigned __int64 v10; // rbx
  int v11; // eax
  int v12; // ecx
  DWORD CurrentThreadId; // [rsp+88h] [rbp-29h]
  LARGE_INTEGER PerformanceCount; // [rsp+90h] [rbp-21h] BYREF
  unsigned __int64 v16; // [rsp+98h] [rbp-19h] BYREF
  wchar_t *Buffer; // [rsp+A0h] [rbp-11h] BYREF
  wchar_t *v18; // [rsp+A8h] [rbp-9h]
  struct _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp-1h] BYREF

  v18 = a1;
  Buffer = 0;
  v16 = 0;
  SystemTime = 0;
  PerformanceCount.QuadPart = 0;
  GetLocalTime(&SystemTime);
  if ( !QueryPerformanceCounter(&PerformanceCount) )
    return (unsigned int)-2147467259;
  CurrentThreadId = GetCurrentThreadId();
  v7 = StringCchPrintfExW(
         v18,
         0x1000u,
         &Buffer,
         &v16,
         0,
         L"[%I64u] [%u-%02u-%02u %02u:%02u:%02u.%03u] %s [%X.%X.%X] ",
         PerformanceCount.QuadPart,
         SystemTime.wYear,
         SystemTime.wMonth,
         SystemTime.wDay,
         SystemTime.wHour,
         SystemTime.wMinute,
         SystemTime.wSecond,
         SystemTime.wMilliseconds,
         &BaseName,
         pSessionId,
         dword_1400130D0,
         CurrentThreadId);
  if ( (v7 & 0x80000000) != 0 )
    return v7;
  v8 = v16;
  v7 = -2147024809;
  v9 = Buffer;
  if ( v16 )
  {
    if ( v16 > 0x7FFFFFFF )
    {
      *Buffer = 0;
      return v7;
    }
    v10 = v16 - 1;
    v11 = _vsnwprintf(Buffer, v16 - 1, a4, Args);
    if ( v11 < 0 || v11 > v10 )
    {
      v12 = -2147024774;
    }
    else
    {
      v12 = 0;
      if ( v11 != v10 )
      {
        v10 = v11;
LABEL_12:
        v8 -= v10;
        goto LABEL_13;
      }
    }
    v9[v10] = 0;
    goto LABEL_12;
  }
  v12 = -2147024809;
LABEL_13:
  v7 = v12;
  if ( v12 >= 0 )
    *a3 = 4096 - v8;
  return v7;
}

```

## disassembly

```asm
0x14000404c  mov     [rsp-8+arg_8], rbx
0x140004051  push    rbp
0x140004052  push    rsi
0x140004053  push    rdi
0x140004054  push    r12
0x140004056  push    r13
0x140004058  push    r14
0x14000405a  push    r15
0x14000405c  lea     rbp, [rsp-1Fh]
0x140004061  sub     rsp, 0D0h
0x140004068  mov     rax, cs:__security_cookie
0x14000406f  xor     rax, rsp
0x140004072  mov     [rbp+4Fh+var_40], rax
0x140004076  mov     r12, [rbp+4Fh+Args]
0x14000407a  xor     ebx, ebx
0x14000407c  mov     [rbp+4Fh+var_58], rcx
0x140004080  xorps   xmm0, xmm0
0x140004083  lea     rcx, [rbp+4Fh+SystemTime]; lpSystemTime
0x140004087  mov     [rbp+4Fh+Buffer], rbx
0x14000408b  mov     [rbp+4Fh+var_68], rbx
0x14000408f  mov     r15, r9
0x140004092  movups  xmmword ptr [rbp+4Fh+SystemTime.wYear], xmm0
0x140004096  mov     qword ptr [rbp+4Fh+PerformanceCount], rbx
0x14000409a  mov     r13, r8
0x14000409d  call    cs:__imp_GetLocalTime
0x1400040a3  lea     rcx, [rbp+4Fh+PerformanceCount]; lpPerformanceCount
0x1400040a7  call    cs:__imp_QueryPerformanceCounter
0x1400040ad  test    eax, eax
0x1400040af  jnz     short loc_1400040BB
0x1400040b1  mov     edx, 80004005h
0x1400040b6  jmp     loc_1400041E4
0x1400040bb  call    cs:__imp_GetCurrentThreadId
0x1400040c1  mov     ecx, cs:dword_1400130D0
0x1400040c7  mov     edx, cs:pSessionId
0x1400040cd  movzx   r8d, [rbp+4Fh+SystemTime.wMilliseconds]
0x1400040d2  movzx   r9d, [rbp+4Fh+SystemTime.wSecond]
0x1400040d7  mov     r14, qword ptr [rbp+4Fh+PerformanceCount]
0x1400040db  movzx   r10d, [rbp+4Fh+SystemTime.wMinute]
0x1400040e0  movzx   r11d, [rbp+4Fh+SystemTime.wHour]
0x1400040e5  movzx   ebx, [rbp+4Fh+SystemTime.wDay]
0x1400040e9  movzx   edi, [rbp+4Fh+SystemTime.wMonth]
0x1400040ed  movzx   esi, [rbp+4Fh+SystemTime.wYear]
0x1400040f1  mov     [rsp+100h+var_78], eax
0x1400040f8  lea     rax, BaseName
0x1400040ff  mov     [rsp+100h+var_80], ecx
0x140004106  mov     rcx, [rbp+4Fh+var_58]; Buffer
0x14000410a  mov     [rsp+100h+var_88], edx
0x14000410e  mov     [rsp+100h+var_90], rax
0x140004113  lea     rax, aI64uU02u02u02u; "[%I64u] [%u-%02u-%02u %02u:%02u:%02u.%0"...
0x14000411a  mov     [rsp+100h+var_98], r8d
0x14000411f  lea     r8, [rbp+4Fh+Buffer]; unsigned __int16 **
0x140004123  mov     [rsp+100h+var_A0], r9d
0x140004128  lea     r9, [rbp+4Fh+var_68]; unsigned __int64 *
0x14000412c  mov     [rsp+100h+var_A8], r10d
0x140004131  mov     [rsp+100h+var_B0], r11d
0x140004136  mov     [rsp+100h+var_B8], ebx
0x14000413a  mov     [rsp+100h+var_C0], edi
0x14000413e  mov     [rsp+100h+var_C8], esi
0x140004142  mov     [rsp+100h+var_D0], r14
0x140004147  mov     r14d, 1000h
0x14000414d  mov     [rsp+100h+var_D8], rax; unsigned __int16 *
0x140004152  mov     edx, r14d; unsigned __int64
0x140004155  mov     qword ptr [rsp+100h+var_E0], 0; unsigned int
0x14000415e  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x140004163  mov     edx, eax
0x140004165  test    eax, eax
0x140004167  js      short loc_1400041E4
0x140004169  mov     rdi, [rbp+4Fh+var_68]
0x14000416d  mov     edx, 80070057h
0x140004172  mov     rsi, [rbp+4Fh+Buffer]
0x140004176  test    rdi, rdi
0x140004179  jz      loc_14000420D
0x14000417f  cmp     rdi, 7FFFFFFFh
0x140004186  ja      loc_140004214
0x14000418c  lea     rbx, [rdi-1]
0x140004190  mov     r9, r12; Args
0x140004193  mov     rdx, rbx; BufferCount
0x140004196  mov     r8, r15; Format
0x140004199  mov     rcx, rsi; Buffer
0x14000419c  call    cs:__imp__vsnwprintf
0x1400041a2  mov     edx, 8007007Ah
0x1400041a7  test    eax, eax
0x1400041a9  js      short loc_1400041BE
0x1400041ab  cdqe
0x1400041ad  cmp     rax, rbx
0x1400041b0  ja      short loc_1400041BE
0x1400041b2  xor     ecx, ecx
0x1400041b4  cmp     rax, rbx
0x1400041b7  jz      short loc_1400041C0
0x1400041b9  mov     rbx, rax
0x1400041bc  jmp     short loc_1400041C6
0x1400041be  mov     ecx, edx
0x1400041c0  xor     eax, eax
0x1400041c2  mov     [rsi+rbx*2], ax
0x1400041c6  mov     rax, rdi
0x1400041c9  sub     rax, rbx
0x1400041cc  test    ecx, ecx
0x1400041ce  jns     short loc_1400041D4
0x1400041d0  cmp     ecx, edx
0x1400041d2  jnz     short loc_1400041D7
0x1400041d4  mov     rdi, rax
0x1400041d7  mov     edx, ecx
0x1400041d9  test    ecx, ecx
0x1400041db  js      short loc_1400041E4
0x1400041dd  sub     r14, rdi
0x1400041e0  mov     [r13+0], r14
0x1400041e4  mov     eax, edx
0x1400041e6  mov     rcx, [rbp+4Fh+var_40]
0x1400041ea  xor     rcx, rsp; StackCookie
0x1400041ed  call    __security_check_cookie
0x1400041f2  mov     rbx, [rsp+100h+arg_8]
0x1400041fa  add     rsp, 0D0h
0x140004201  pop     r15
0x140004203  pop     r14
0x140004205  pop     r13
0x140004207  pop     r12
0x140004209  pop     rdi
0x14000420a  pop     rsi
0x14000420b  pop     rbp
0x14000420c  retn
0x14000420d  mov     ecx, edx
0x14000420f  test    rdi, rdi
0x140004212  jz      short loc_1400041D7
0x140004214  xor     eax, eax
0x140004216  mov     [rsi], ax
0x140004219  jmp     short loc_1400041E4
```
