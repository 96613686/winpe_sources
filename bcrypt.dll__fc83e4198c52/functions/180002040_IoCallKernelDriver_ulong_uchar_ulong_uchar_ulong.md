# IoCallKernelDriver(ulong,uchar *,ulong,uchar *,ulong *)

- ea: `0x180002040`
- end: `0x180002233`
- name: `?IoCallKernelDriver@@YAJKPEAEK0PEAK@Z`
- size: `499`
- prototype: `NTSTATUS __fastcall(int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `15`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800023f0`
- `0x1800030a0`
- `0x18000997c`
- `0x180012780`
- `0x180013330`
- `0x180013510`
- `0x180013720`
- `0x1800138c0`
- `0x1800186e0`
- `0x180018860`
- `0x180018a00`
- `0x1800195e0`
- `0x180019770`
- `0x180019a00`
- `0x180019b1c`

## callees

- `0x180002040`
- `0x1800022cc`
- `0x18001b79d`
- `0x18001b7e0`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x1800020ff`
- `ntdll!NtDeviceIoControlFile` at `0x1800020ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800021bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800021bf`

## pseudocode

```c
NTSTATUS __fastcall IoCallKernelDriver(
        int a1,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  unsigned __int8 *InputBuffer; // rdi
  ULONG InputBufferLength; // ebp
  ULONG OutputBufferLength; // r15d
  unsigned __int8 *OutputBuffer; // r14
  NTSTATUS result; // eax
  unsigned int Information; // edi
  int v12; // ecx
  int v13; // r12d
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-68h] BYREF
  char Src; // [rsp+60h] [rbp-58h] BYREF
  char v16; // [rsp+68h] [rbp-50h] BYREF

  IoStatusBlock = 0;
  if ( a2 && a3 < 8 )
    return -1073741595;
  InputBuffer = (unsigned __int8 *)&v16;
  InputBufferLength = 8;
  if ( a2 )
  {
    InputBuffer = a2;
    InputBufferLength = a3;
  }
  *(_DWORD *)InputBuffer = 439041101;
  *((_DWORD *)InputBuffer + 1) = a1;
  if ( a5 )
    OutputBufferLength = *a5;
  else
    OutputBufferLength = 0;
  if ( a4 && OutputBufferLength >= 8 )
  {
    OutputBuffer = a4;
  }
  else
  {
    OutputBuffer = (unsigned __int8 *)&Src;
    OutputBufferLength = 8;
  }
  if ( !g_hIoDevice )
  {
    v13 = 0;
    EnterCriticalSection(&g_csIoInitialize);
    if ( !g_hIoDevice )
      v13 = _IoOpenDevice();
    LeaveCriticalSection(&g_csIoInitialize);
    if ( v13 < 0 )
      return v13;
  }
  result = NtDeviceIoControlFile(
             g_hIoDevice,
             0,
             0,
             0,
             &IoStatusBlock,
             0x390400u,
             InputBuffer,
             InputBufferLength,
             OutputBuffer,
             OutputBufferLength);
  Information = IoStatusBlock.Information;
  if ( result < 0 )
  {
    if ( result != -1073741789 )
    {
      if ( result != -2147483643 )
        return result;
      if ( LODWORD(IoStatusBlock.Information) >= 4 )
      {
        v12 = *(_DWORD *)OutputBuffer;
        if ( *(_DWORD *)OutputBuffer != -1073741789 )
        {
          if ( LODWORD(IoStatusBlock.Information) != 4 )
            return -1073741595;
          return v12;
        }
        if ( LODWORD(IoStatusBlock.Information) == 8 )
        {
          if ( a5 )
            *a5 = *((_DWORD *)OutputBuffer + 1);
          return -1073741789;
        }
      }
    }
    return -1073741595;
  }
  if ( a5 )
  {
    if ( !a4 || *a5 < LODWORD(IoStatusBlock.Information) )
    {
      *a5 = IoStatusBlock.Information;
      return -1073741789;
    }
    if ( OutputBuffer == (unsigned __int8 *)&Src )
      memcpy_0(a4, OutputBuffer, LODWORD(IoStatusBlock.Information));
    *a5 = Information;
  }
  return 0;
}

```

## disassembly

```asm
0x180002040  push    rbx
0x180002042  push    rbp
0x180002043  push    rsi
0x180002044  push    rdi
0x180002045  push    r12
0x180002047  push    r14
0x180002049  push    r15
0x18000204b  sub     rsp, 80h
0x180002052  mov     rax, cs:__security_cookie
0x180002059  xor     rax, rsp
0x18000205c  mov     [rsp+0B8h+var_48], rax
0x180002061  mov     rbx, [rsp+0B8h+arg_20]
0x180002069  xorps   xmm0, xmm0
0x18000206c  mov     rsi, r9
0x18000206f  movups  xmmword ptr [rsp+0B8h+var_68], xmm0
0x180002074  test    rdx, rdx
0x180002077  jnz     loc_180002177
0x18000207d  test    rdx, rdx
0x180002080  lea     rdi, [rsp+0B8h+var_50]
0x180002085  mov     ebp, 8
0x18000208a  cmovnz  rdi, rdx
0x18000208e  cmovnz  ebp, r8d
0x180002092  mov     dword ptr [rdi], 1A2B3C4Dh
0x180002098  mov     [rdi+4], ecx
0x18000209b  test    rbx, rbx
0x18000209e  jz      loc_180002183
0x1800020a4  mov     r15d, [rbx]
0x1800020a7  test    rsi, rsi
0x1800020aa  jnz     loc_180002165
0x1800020b0  lea     r14, [rsp+0B8h+Src]
0x1800020b5  mov     r15d, 8
0x1800020bb  mov     rax, cs:?g_hIoDevice@@3REAXEA; void * g_hIoDevice
0x1800020c2  test    rax, rax
0x1800020c5  jz      loc_1800021B5
0x1800020cb  mov     rcx, cs:?g_hIoDevice@@3REAXEA; FileHandle
0x1800020d2  lea     rax, [rsp+0B8h+var_68]
0x1800020d7  mov     [rsp+0B8h+OutputBufferLength], r15d; OutputBufferLength
0x1800020dc  xor     r9d, r9d; ApcContext
0x1800020df  mov     [rsp+0B8h+OutputBuffer], r14; OutputBuffer
0x1800020e4  xor     r8d, r8d; ApcRoutine
0x1800020e7  mov     [rsp+0B8h+InputBufferLength], ebp; InputBufferLength
0x1800020eb  xor     edx, edx; Event
0x1800020ed  mov     [rsp+0B8h+InputBuffer], rdi; InputBuffer
0x1800020f2  mov     [rsp+0B8h+IoControlCode], 390400h; IoControlCode
0x1800020fa  mov     [rsp+0B8h+IoStatusBlock], rax; IoStatusBlock
0x1800020ff  call    cs:__imp_NtDeviceIoControlFile
0x180002106  nop     dword ptr [rax+rax+00h]
0x18000210b  mov     edi, dword ptr [rsp+0B8h+var_68.Information]
0x18000210f  test    eax, eax
0x180002111  js      short loc_18000218B
0x180002113  test    rbx, rbx
0x180002116  jz      short loc_180002143
0x180002118  test    rsi, rsi
0x18000211b  jz      loc_180002227
0x180002121  cmp     [rbx], edi
0x180002123  jb      loc_180002227
0x180002129  lea     rax, [rsp+0B8h+Src]
0x18000212e  cmp     r14, rax
0x180002131  jnz     short loc_180002141
0x180002133  mov     r8d, edi; Size
0x180002136  mov     rdx, r14; Src
0x180002139  mov     rcx, rsi; void *
0x18000213c  call    memcpy_0
0x180002141  mov     [rbx], edi
0x180002143  xor     eax, eax
0x180002145  mov     rcx, [rsp+0B8h+var_48]
0x18000214a  xor     rcx, rsp; StackCookie
0x18000214d  call    __security_check_cookie
0x180002152  add     rsp, 80h
0x180002159  pop     r15
0x18000215b  pop     r14
0x18000215d  pop     r12
0x18000215f  pop     rdi
0x180002160  pop     rsi
0x180002161  pop     rbp
0x180002162  pop     rbx
0x180002163  retn
0x180002165  cmp     r15d, 8
0x180002169  jb      loc_1800020B0
0x18000216f  mov     r14, rsi
0x180002172  jmp     loc_1800020BB
0x180002177  cmp     r8d, 8
0x18000217b  jnb     loc_18000207D
0x180002181  jmp     short loc_1800021AE
0x180002183  xor     r15d, r15d
0x180002186  jmp     loc_1800020A7
0x18000218b  cmp     eax, 0C0000023h
0x180002190  jz      short loc_1800021AE
0x180002192  cmp     eax, 80000005h
0x180002197  jnz     short loc_180002145
0x180002199  cmp     edi, 4
0x18000219c  jb      short loc_1800021AE
0x18000219e  mov     ecx, [r14]
0x1800021a1  cmp     ecx, 0C0000023h
0x1800021a7  jnz     short loc_180002215
0x1800021a9  cmp     edi, 8
0x1800021ac  jz      short loc_180002203
0x1800021ae  mov     eax, 0C00000E5h
0x1800021b3  jmp     short loc_180002145
0x1800021b5  lea     rcx, ?g_csIoInitialize@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800021bc  xor     r12d, r12d
0x1800021bf  call    cs:__imp_EnterCriticalSection
0x1800021c6  nop     dword ptr [rax+rax+00h]
0x1800021cb  mov     rax, cs:?g_hIoDevice@@3REAXEA; void * g_hIoDevice
0x1800021d2  test    rax, rax
0x1800021d5  jnz     short loc_1800021DF
0x1800021d7  call    ?_IoOpenDevice@@YAJXZ; _IoOpenDevice(void)
0x1800021dc  mov     r12d, eax
0x1800021df  lea     rcx, ?g_csIoInitialize@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800021e6  call    cs:__imp_LeaveCriticalSection
0x1800021ed  nop     dword ptr [rax+rax+00h]
0x1800021f2  test    r12d, r12d
0x1800021f5  jns     loc_1800020CB
0x1800021fb  mov     eax, r12d
0x1800021fe  jmp     loc_180002145
0x180002203  test    rbx, rbx
0x180002206  jz      short loc_18000220E
0x180002208  mov     eax, [r14+4]
0x18000220c  mov     [rbx], eax
0x18000220e  mov     eax, ecx
0x180002210  jmp     loc_180002145
0x180002215  mov     eax, 0C00000E5h
0x18000221a  cmp     edi, 4
0x18000221d  cmovnz  ecx, eax
0x180002220  mov     eax, ecx
0x180002222  jmp     loc_180002145
0x180002227  mov     [rbx], edi
0x180002229  mov     eax, 0C0000023h
0x18000222e  jmp     loc_180002145
```
