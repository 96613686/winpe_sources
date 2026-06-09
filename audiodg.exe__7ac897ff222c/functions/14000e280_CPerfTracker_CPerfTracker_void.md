# CPerfTracker::~CPerfTracker(void)

- ea: `0x14000e280`
- end: `0x14000e3fe`
- name: `??1CPerfTracker@@QEAA@XZ`
- size: `382`
- prototype: `void __fastcall(CPerfTracker *__hidden this)`
- caller_count: `45`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140006f20`
- `0x14000c430`
- `0x14000c760`
- `0x14000ca20`
- `0x14000cc80`
- `0x14000d150`
- `0x14000d2d0`
- `0x14000d5f8`
- `0x14000d710`
- `0x14000d9e0`
- `0x14000db44`
- `0x140011c40`
- `0x14001c678`
- `0x14001e34c`
- `0x14002ac14`
- `0x140033df0`
- `0x140035b30`
- `0x14003a4e0`
- `0x14003e0b0`
- `0x140040650`
- `0x140040810`
- `0x140040ce0`
- `0x140044e70`
- `0x140049370`
- `0x14004d5a0`
- `0x140066410`
- `0x140066620`
- `0x1400666d0`
- `0x140066780`
- `0x1400669b0`
- `0x140066be0`
- `0x140066c90`
- `0x14007c060`
- `0x14007d170`
- `0x14007d430`
- `0x14007d5f0`
- `0x140081750`
- `0x1400ad818`
- `0x1400ad8c5`
- `0x1400ae1db`
- `0x1400ae322`
- `0x1400aede6`
- `0x1400aedf8`
- `0x1400aff76`
- `0x1400b2373`

## callees

- `0x14000df10`
- `0x14000e200`
- `0x14000e280`
- `0x14000e680`
- `0x14005d0e0`
- `0x14005e168`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e3b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e3b3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000e2e3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000e2e3`
- `ntdll!EtwEventActivityIdControl` at `0x14000e31e`
- `ntdll!EtwEventActivityIdControl` at `0x14000e31e`

## pseudocode

```c
void __fastcall CPerfTracker::~CPerfTracker(CPerfTracker *this)
{
  double v2; // xmm6_8
  DWORD CurrentThreadId; // eax
  _QWORD v4[3]; // [rsp+70h] [rbp-98h] BYREF
  char v5[272]; // [rsp+88h] [rbp-80h] BYREF

  StringCchPrintfExA(*((STRSAFE_LPSTR *)this + 27), *((_QWORD *)this + 28), 0, 0, 0, "-Stop");
  QueryPerformanceCounter((LARGE_INTEGER *)this + 1);
  v2 = 0.0;
  if ( *((_QWORD *)this + 2) )
    v2 = (double)(*((_DWORD *)this + 2) - *(_DWORD *)this) / (double)(int)*((_QWORD *)this + 2);
  *(_OWORD *)&v4[1] = 0;
  EtwEventActivityIdControl(1, &v4[1]);
  memset_0(v5, 0, 0x104u);
  StringCchPrintfA(
    v5,
    0x104u,
    "{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
    LODWORD(v4[1]),
    WORD2(v4[1]),
    HIWORD(v4[1]),
    LOBYTE(v4[2]),
    BYTE1(v4[2]),
    BYTE2(v4[2]),
    BYTE3(v4[2]),
    BYTE4(v4[2]),
    BYTE5(v4[2]),
    BYTE6(v4[2]),
    HIBYTE(v4[2]));
  CurrentThreadId = GetCurrentThreadId();
  UpdateAudioActivityPerfTracker(
    (CPerfTracker *)((char *)this + 88),
    CurrentThreadId,
    v5,
    (const char *const)this + 24,
    (const char *const)this + 88,
    v2);
}

```

## disassembly

```asm
0x14000e280  mov     rax, rsp
0x14000e283  push    rbp
0x14000e284  push    rbx
0x14000e285  push    rsi
0x14000e286  push    rdi
0x14000e287  push    r14
0x14000e289  push    r15
0x14000e28b  lea     rbp, [rax-0E8h]
0x14000e292  sub     rsp, 1B8h
0x14000e299  movaps  xmmword ptr [rax-48h], xmm6
0x14000e29d  mov     rax, cs:__security_cookie
0x14000e2a4  xor     rax, rsp
0x14000e2a7  mov     [rbp+0E0h+var_50], rax
0x14000e2ae  mov     rdx, [rcx+0E0h]; cbDest
0x14000e2b5  lea     rax, aStop; "-Stop"
0x14000e2bc  mov     r15, rcx
0x14000e2bf  mov     [rsp+1E0h+var_1B8], rax; char *
0x14000e2c4  mov     rcx, [rcx+0D8h]; pszDest
0x14000e2cb  xor     r9d, r9d; unsigned __int64 *
0x14000e2ce  xor     r8d, r8d; char **
0x14000e2d1  mov     qword ptr [rsp+1E0h+var_1C0], 0; DWORD
0x14000e2da  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x14000e2df  lea     rcx, [r15+8]; lpPerformanceCount
0x14000e2e3  call    cs:__imp_QueryPerformanceCounter
0x14000e2e9  cmp     qword ptr [r15+10h], 0
0x14000e2ee  xorps   xmm6, xmm6
0x14000e2f1  jz      short loc_14000E30C
0x14000e2f3  mov     rax, [r15+8]
0x14000e2f7  xorps   xmm0, xmm0
0x14000e2fa  sub     rax, [r15]
0x14000e2fd  cvtsi2sd xmm0, qword ptr [r15+10h]
0x14000e303  cvtsi2sd xmm6, rax
0x14000e308  divsd   xmm6, xmm0
0x14000e30c  xorps   xmm0, xmm0
0x14000e30f  lea     rdx, [rsp+1E0h+var_178+8]
0x14000e314  mov     ecx, 1
0x14000e319  movups  xmmword ptr [rsp+1E0h+var_178+8], xmm0
0x14000e31e  call    cs:__imp_EtwEventActivityIdControl
0x14000e324  xor     edx, edx; Val
0x14000e326  lea     rcx, [rbp+0E0h+var_160]; void *
0x14000e32a  mov     r8d, 104h; Size
0x14000e330  call    memset_0
0x14000e335  movzx   ecx, [rsp+1E0h+var_178+16h]
0x14000e33a  mov     edx, 104h; unsigned __int64
0x14000e33f  movzx   r8d, [rsp+1E0h+var_178+15h]
0x14000e345  movzx   r9d, [rsp+1E0h+var_178+14h]
0x14000e34b  movzx   eax, [rsp+1E0h+var_178+17h]
0x14000e350  movzx   r10d, [rsp+1E0h+var_178+13h]
0x14000e356  movzx   r11d, [rsp+1E0h+var_178+12h]
0x14000e35c  movzx   ebx, [rsp+1E0h+var_178+11h]
0x14000e361  movzx   edi, [rsp+1E0h+var_178+10h]
0x14000e366  movzx   esi, word ptr [rsp+1E0h+var_178+0Eh]
0x14000e36b  movzx   r14d, word ptr [rsp+1E0h+var_178+0Ch]
0x14000e371  mov     dword ptr [rsp+1E0h+var_178], eax
0x14000e375  mov     [rsp+1E0h+var_180], ecx
0x14000e379  lea     rcx, [rbp+0E0h+var_160]; char *
0x14000e37d  mov     [rsp+1E0h+var_188], r8d
0x14000e382  lea     r8, a08x04x04x02x02; "{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%0"...
0x14000e389  mov     [rsp+1E0h+var_190], r9d
0x14000e38e  mov     r9d, dword ptr [rsp+1E0h+var_178+8]
0x14000e393  mov     [rsp+1E0h+var_198], r10d
0x14000e398  mov     [rsp+1E0h+var_1A0], r11d
0x14000e39d  mov     [rsp+1E0h+var_1A8], ebx
0x14000e3a1  mov     [rsp+1E0h+var_1B0], edi
0x14000e3a5  mov     dword ptr [rsp+1E0h+var_1B8], esi
0x14000e3a9  mov     [rsp+1E0h+var_1C0], r14d
0x14000e3ae  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14000e3b3  call    cs:__imp_GetCurrentThreadId
0x14000e3b9  lea     rcx, [r15+58h]; struct _tlgProvider_t *
0x14000e3bd  movsd   [rsp+1E0h+var_1B8], xmm6; double
0x14000e3c3  mov     edx, eax; unsigned int
0x14000e3c5  mov     qword ptr [rsp+1E0h+var_1C0], rcx; char *
0x14000e3ca  lea     r9, [r15+18h]; char *
0x14000e3ce  lea     r8, [rbp+0E0h+var_160]; char *
0x14000e3d2  call    ?UpdateAudioActivityPerfTracker@@YAXPEBU_tlgProvider_t@@KQEBD11N@Z; UpdateAudioActivityPerfTracker(_tlgProvider_t const *,ulong,char const * const,char const * const,char const * const,double)
0x14000e3d7  mov     rcx, [rbp+0E0h+var_50]
0x14000e3de  xor     rcx, rsp; StackCookie
0x14000e3e1  call    __security_check_cookie
0x14000e3e6  movaps  xmm6, [rsp+1E0h+var_48+8]
0x14000e3ee  add     rsp, 1B8h
0x14000e3f5  pop     r15
0x14000e3f7  pop     r14
0x14000e3f9  pop     rdi
0x14000e3fa  pop     rsi
0x14000e3fb  pop     rbx
0x14000e3fc  pop     rbp
0x14000e3fd  retn
```
