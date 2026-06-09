# Rdp::Modern::Utils::CInflightRecorder::WriteToBufferInternal(char *,char *,unsigned __int64)

- ea: `0x180020194`
- end: `0x180020406`
- name: `?WriteToBufferInternal@CInflightRecorder@Utils@Modern@Rdp@@AEAA_KPEAD0_K@Z`
- size: `626`
- prototype: `unsigned __int64 __fastcall(Rdp::Modern::Utils::CInflightRecorder *__hidden this, char *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800200ec`

## callees

- `0x180006f60`
- `0x1800073d0`
- `0x180007b38`
- `0x18001db68`
- `0x180020194`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180020318`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180020318`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800201e7`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800201e7`

## pseudocode

```c
unsigned __int64 __fastcall Rdp::Modern::Utils::CInflightRecorder::WriteToBufferInternal(
        Rdp::Modern::Utils::CInflightRecorder *this,
        char *a2,
        char *a3,
        __int64 a4)
{
  __int64 v5; // rcx
  __int64 v6; // rsi
  __int64 v9; // r14
  int v10; // ecx
  const char *v11; // r15
  int v12; // ecx
  int v13; // ecx
  __int64 v14; // r9
  const char *v15; // r8
  unsigned __int64 v17; // [rsp+A0h] [rbp-80h] BYREF
  char *v18; // [rsp+A8h] [rbp-78h]
  _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp-70h] BYREF
  char Buffer[16]; // [rsp+C0h] [rbp-60h] BYREF
  __int128 v21; // [rsp+D0h] [rbp-50h]
  char v22[256]; // [rsp+E0h] [rbp-40h] BYREF
  CHAR MultiByteStr[256]; // [rsp+1E0h] [rbp+C0h] BYREF

  v18 = a2;
  v5 = *((_QWORD *)this + 1);
  v6 = 176 * a4;
  SystemTime = 0;
  FileTimeToSystemTime((const FILETIME *)(176 * a4 + v5), &SystemTime);
  v9 = *((_QWORD *)this + 1);
  if ( !*(_QWORD *)(v6 + v9 + 64) )
    return 0;
  v10 = *(_DWORD *)(v6 + v9 + 8);
  v11 = 0;
  if ( v10 )
  {
    v12 = v10 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        if ( v13 == 1 )
          v11 = "BUGCHECK: ";
      }
      else
      {
        v11 = "LOG: ";
        if ( *(int *)(v6 + v9 + 16) < 0 )
          v11 = "ERROR: ";
      }
    }
    else
    {
      v11 = "RETURN: ";
    }
  }
  else
  {
    v11 = "EXCEPTION: ";
  }
  *(_OWORD *)Buffer = 0;
  v21 = 0;
  v14 = *(unsigned int *)(v6 + v9 + 16);
  if ( (int)v14 < 0 )
  {
    if ( (*(_DWORD *)(v6 + v9 + 12) & 8) != 0 )
      v14 = *(unsigned int *)(v6 + v9 + 20);
    v15 = ", status:%#x";
    if ( (*(_DWORD *)(v6 + v9 + 12) & 8) == 0 )
      v15 = ", hr:%#x";
    sprintf_s(Buffer, 0x20u, v15, v14);
  }
  strcpy(v22, "\n");
  memset_0(&v22[2], 0, 0xFEu);
  if ( !*(_QWORD *)(v6 + v9 + 32) )
    sprintf_s(v22, 0x100u, ", file:\"%s\", line:%d\n", *(const char **)(v6 + v9 + 64), *(_DWORD *)(v6 + v9 + 72));
  memset_0(MultiByteStr, 0, sizeof(MultiByteStr));
  if ( !WideCharToMultiByte(0xFDE9u, 0, *(LPCWCH *)(v6 + v9 + 32), -1, MultiByteStr, 256, 0, 0) )
    MultiByteStr[0] = 0;
  v17 = 0;
  if ( (int)StringCchPrintfExA(
              v18,
              a3 - v18,
              0,
              &v17,
              0x100u,
              "[%zu@%04d-%02d-%02dT%02d:%02d:%02d.%03d %x] %s\"%s\"%s%s",
              a4,
              SystemTime.wYear,
              SystemTime.wMonth,
              SystemTime.wDay,
              SystemTime.wHour,
              SystemTime.wMinute,
              SystemTime.wSecond,
              SystemTime.wMilliseconds,
              *(_DWORD *)(v6 + v9 + 40),
              v11,
              MultiByteStr,
              Buffer,
              v22) >= 0 )
    return v17;
  else
    return 0;
}

```

## disassembly

```asm
0x180020194  push    rbp
0x180020196  push    rbx
0x180020197  push    rsi
0x180020198  push    rdi
0x180020199  push    r12
0x18002019b  push    r13
0x18002019d  push    r14
0x18002019f  push    r15
0x1800201a1  lea     rbp, [rsp-1D8h]
0x1800201a9  sub     rsp, 2F8h
0x1800201b0  mov     rax, cs:__security_cookie
0x1800201b7  xor     rax, rsp
0x1800201ba  mov     [rbp+210h+var_50], rax
0x1800201c1  mov     rbx, rcx
0x1800201c4  mov     [rbp+210h+var_288], rdx
0x1800201c8  mov     rcx, [rcx+8]
0x1800201cc  lea     rdx, [rbp+210h+SystemTime]; lpSystemTime
0x1800201d0  imul    rsi, r9, 0B0h
0x1800201d7  xorps   xmm0, xmm0
0x1800201da  movups  xmmword ptr [rbp+210h+SystemTime.wYear], xmm0
0x1800201de  mov     r13, r9
0x1800201e1  mov     r12, r8
0x1800201e4  add     rcx, rsi; lpFileTime
0x1800201e7  call    cs:__imp_FileTimeToSystemTime
0x1800201ee  nop     dword ptr [rax+rax+00h]
0x1800201f3  mov     r14, [rbx+8]
0x1800201f7  xor     ebx, ebx
0x1800201f9  cmp     [rsi+r14+40h], rbx
0x1800201fe  jz      loc_1800203E0
0x180020204  mov     ecx, [rsi+r14+8]
0x180020209  mov     r15d, ebx
0x18002020c  test    ecx, ecx
0x18002020e  jz      short loc_18002024A
0x180020210  sub     ecx, 1
0x180020213  jz      short loc_180020241
0x180020215  sub     ecx, 1
0x180020218  jz      short loc_180020228
0x18002021a  cmp     ecx, 1
0x18002021d  jnz     short loc_180020251
0x18002021f  lea     r15, aBugcheck; "BUGCHECK: "
0x180020226  jmp     short loc_180020251
0x180020228  cmp     [rsi+r14+10h], ebx
0x18002022d  lea     rax, aError; "ERROR: "
0x180020234  lea     r15, aLog; "LOG: "
0x18002023b  cmovl   r15, rax
0x18002023f  jmp     short loc_180020251
0x180020241  lea     r15, aReturn; "RETURN: "
0x180020248  jmp     short loc_180020251
0x18002024a  lea     r15, aException_0; "EXCEPTION: "
0x180020251  xorps   xmm0, xmm0
0x180020254  movups  xmmword ptr [rbp+210h+Buffer], xmm0
0x180020258  movups  [rbp+210h+var_260], xmm0
0x18002025c  mov     r9d, [rsi+r14+10h]
0x180020261  test    r9d, r9d
0x180020264  jns     short loc_180020297
0x180020266  mov     eax, [rsi+r14+0Ch]
0x18002026b  and     eax, 8
0x18002026e  jz      short loc_180020275
0x180020270  mov     r9d, [rsi+r14+14h]
0x180020275  test    eax, eax
0x180020277  lea     rcx, aHrX; ", hr:%#x"
0x18002027e  lea     r8, aStatusX; ", status:%#x"
0x180020285  mov     edx, 20h ; ' '; BufferCount
0x18002028a  cmovz   r8, rcx; Format
0x18002028e  lea     rcx, [rbp+210h+Buffer]; Buffer
0x180020292  call    sprintf_s
0x180020297  mov     eax, 0Ah
0x18002029c  lea     rcx, [rbp+210h+var_250+2]; void *
0x1800202a0  xor     edx, edx; Val
0x1800202a2  mov     word ptr [rbp+210h+var_250], ax
0x1800202a6  mov     r8d, 0FEh; Size
0x1800202ac  call    memset_0
0x1800202b1  mov     edi, 100h
0x1800202b6  cmp     [rsi+r14+20h], rbx
0x1800202bb  jnz     short loc_1800202DD
0x1800202bd  mov     eax, [rsi+r14+48h]
0x1800202c2  lea     r8, aFileSLineD; ", file:\"%s\", line:%d\n"
0x1800202c9  mov     r9, [rsi+r14+40h]
0x1800202ce  lea     rcx, [rbp+210h+var_250]; Buffer
0x1800202d2  mov     edx, edi; BufferCount
0x1800202d4  mov     dword ptr [rsp+330h+lpMultiByteStr], eax
0x1800202d8  call    sprintf_s
0x1800202dd  mov     r8, rdi; Size
0x1800202e0  lea     rcx, [rbp+210h+MultiByteStr]; void *
0x1800202e7  xor     edx, edx; Val
0x1800202e9  call    memset_0
0x1800202ee  mov     r8, [rsi+r14+20h]; lpWideCharStr
0x1800202f3  lea     rax, [rbp+210h+MultiByteStr]
0x1800202fa  mov     [rsp+330h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x1800202ff  or      r9d, 0FFFFFFFFh; cchWideChar
0x180020303  mov     [rsp+330h+lpDefaultChar], rbx; lpDefaultChar
0x180020308  xor     edx, edx; dwFlags
0x18002030a  mov     [rsp+330h+cbMultiByte], edi; cbMultiByte
0x18002030e  mov     ecx, 0FDE9h; CodePage
0x180020313  mov     [rsp+330h+lpMultiByteStr], rax; lpMultiByteStr
0x180020318  call    cs:__imp_WideCharToMultiByte
0x18002031f  nop     dword ptr [rax+rax+00h]
0x180020324  test    eax, eax
0x180020326  jnz     short loc_18002032E
0x180020328  mov     [rbp+210h+MultiByteStr], bl
0x18002032e  movzx   edx, [rbp+210h+SystemTime.wMilliseconds]
0x180020332  lea     rax, [rbp+210h+var_250]
0x180020336  movzx   r8d, [rbp+210h+SystemTime.wSecond]
0x18002033b  movzx   r9d, [rbp+210h+SystemTime.wMinute]
0x180020340  movzx   r10d, [rbp+210h+SystemTime.wHour]
0x180020345  movzx   r11d, [rbp+210h+SystemTime.wDay]
0x18002034a  movzx   edi, [rbp+210h+SystemTime.wYear]
0x18002034e  mov     rcx, [rbp+210h+var_288]; Buffer
0x180020352  mov     [rsp+330h+var_2A0], rax
0x18002035a  sub     r12, rcx
0x18002035d  lea     rax, [rbp+210h+Buffer]
0x180020361  mov     [rbp+210h+var_290], rbx
0x180020365  movzx   ebx, [rbp+210h+SystemTime.wMonth]
0x180020369  mov     [rsp+330h+var_2A8], rax
0x180020371  lea     rax, [rbp+210h+MultiByteStr]
0x180020378  mov     [rsp+330h+var_2B0], rax
0x180020380  mov     eax, [rsi+r14+28h]
0x180020385  mov     [rsp+330h+var_2B8], r15
0x18002038a  mov     [rsp+330h+var_2C0], eax
0x18002038e  lea     rax, aZu04d02d02dt02; "[%zu@%04d-%02d-%02dT%02d:%02d:%02d.%03d"...
0x180020395  mov     [rsp+330h+var_2C8], edx
0x180020399  mov     rdx, r12; Size
0x18002039c  mov     [rsp+330h+var_2D0], r8d
0x1800203a1  xor     r8d, r8d; char **
0x1800203a4  mov     [rsp+330h+var_2D8], r9d
0x1800203a9  lea     r9, [rbp+210h+var_290]; unsigned __int64 *
0x1800203ad  mov     [rsp+330h+var_2E0], r10d
0x1800203b2  mov     [rsp+330h+var_2E8], r11d
0x1800203b7  mov     [rsp+330h+var_2F0], ebx
0x1800203bb  mov     dword ptr [rsp+330h+lpUsedDefaultChar], edi
0x1800203bf  mov     [rsp+330h+lpDefaultChar], r13
0x1800203c4  mov     qword ptr [rsp+330h+cbMultiByte], rax; char *
0x1800203c9  mov     dword ptr [rsp+330h+lpMultiByteStr], 100h; unsigned int
0x1800203d1  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x1800203d6  test    eax, eax
0x1800203d8  js      short loc_1800203E0
0x1800203da  mov     rax, [rbp+210h+var_290]
0x1800203de  jmp     short loc_1800203E2
0x1800203e0  xor     eax, eax
0x1800203e2  mov     rcx, [rbp+210h+var_50]
0x1800203e9  xor     rcx, rsp; StackCookie
0x1800203ec  call    __security_check_cookie
0x1800203f1  add     rsp, 2F8h
0x1800203f8  pop     r15
0x1800203fa  pop     r14
0x1800203fc  pop     r13
0x1800203fe  pop     r12
0x180020400  pop     rdi
0x180020401  pop     rsi
0x180020402  pop     rbx
0x180020403  pop     rbp
0x180020404  retn
```
