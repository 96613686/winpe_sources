# arrow::internal::ThreadPool::DefaultCapacity(void)

- ea: `0x1800dda00`
- end: `0x1800ddab2`
- name: `?DefaultCapacity@ThreadPool@internal@arrow@@SAHXZ`
- size: `178`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800de000`

## callees

- `0x18001b360`
- `0x1800dc8f0`
- `0x1800dca00`
- `0x1800dda00`
- `0x1800de330`
- `0x18030a1e8`
- `0x180358070`

## string_xrefs

- `0x1800dda0f`: `OMP_NUM_THREADS`
- `0x1800dda28`: `OMP_THREAD_LIMIT`
- `0x1800dda4d`: `c:\source\src\submodules\apache\arrow\cpp\src\arrow\util\thread_pool.cc`
- `0x1800dda88`: `Failed to determine the number of available threads, using a hardcoded arbitrary value`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 arrow::internal::ThreadPool::DefaultCapacity(void)
{
  unsigned int v0; // ebx
  int v1; // eax
  __int64 v2; // rbx
  __int64 v3; // rax
  _BYTE v5[32]; // [rsp+28h] [rbp-20h] BYREF

  v0 = arrow::internal::ParseOMPEnvVar("OMP_NUM_THREADS");
  if ( !v0 )
    v0 = Thrd_hardware_concurrency();
  v1 = arrow::internal::ParseOMPEnvVar("OMP_THREAD_LIMIT");
  if ( v1 > 0 )
  {
    if ( (int)v0 < v1 )
      v1 = v0;
    v0 = v1;
  }
  if ( v0 )
    return v0;
  v2 = arrow::util::ArrowLog::ArrowLog(
         v5,
         "c:\\source\\src\\submodules\\apache\\arrow\\cpp\\src\\arrow\\util\\thread_pool.cc",
         295,
         1);
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2) )
  {
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    std::operator<<<std::char_traits<char>>(
      v3,
      "Failed to determine the number of available threads, using a hardcoded arbitrary value");
  }
  arrow::util::ArrowLog::~ArrowLog((arrow::util::ArrowLog *)v5);
  return 4;
}

```

## disassembly

```asm
0x1800dda00  push    rbx
0x1800dda02  sub     rsp, 40h
0x1800dda06  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x1800dda0f  lea     rcx, aOmpNumThreads; "OMP_NUM_THREADS"
0x1800dda16  call    arrow__internal__ParseOMPEnvVar
0x1800dda1b  mov     ebx, eax
0x1800dda1d  test    eax, eax
0x1800dda1f  jnz     short loc_1800DDA28
0x1800dda21  call    _Thrd_hardware_concurrency
0x1800dda26  mov     ebx, eax
0x1800dda28  lea     rcx, aOmpThreadLimit; "OMP_THREAD_LIMIT"
0x1800dda2f  call    arrow__internal__ParseOMPEnvVar
0x1800dda34  test    eax, eax
0x1800dda36  jle     short loc_1800DDA3F
0x1800dda38  cmp     ebx, eax
0x1800dda3a  cmovl   eax, ebx
0x1800dda3d  mov     ebx, eax
0x1800dda3f  test    ebx, ebx
0x1800dda41  jnz     short loc_1800DDAAA
0x1800dda43  lea     r9d, [rbx+1]
0x1800dda47  mov     r8d, 127h
0x1800dda4d  lea     rdx, aCSourceSrcSubm_14; "c:\\source\\src\\submodules\\apache\\ar"...
0x1800dda54  lea     rcx, [rsp+48h+var_20]
0x1800dda59  call    ??0ArrowLog@util@arrow@@QEAA@PEBDHW4ArrowLogLevel@12@@Z; arrow::util::ArrowLog::ArrowLog(char const *,int,arrow::util::ArrowLogLevel)
0x1800dda5e  mov     rbx, rax
0x1800dda61  mov     rcx, [rax]
0x1800dda64  mov     rax, [rcx+8]
0x1800dda68  mov     rcx, rbx
0x1800dda6b  call    cs:__guard_dispatch_icall_fptr
0x1800dda71  test    al, al
0x1800dda73  jz      short loc_1800DDA95
0x1800dda75  mov     rcx, [rbx]
0x1800dda78  mov     rax, [rcx+10h]
0x1800dda7c  mov     rcx, rbx
0x1800dda7f  call    cs:__guard_dispatch_icall_fptr
0x1800dda85  mov     rcx, rax
0x1800dda88  lea     rdx, aFailedToDeterm; "Failed to determine the number of avail"...
0x1800dda8f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800dda94  nop
0x1800dda95  lea     rcx, [rsp+48h+var_20]; this
0x1800dda9a  call    ??1ArrowLog@util@arrow@@UEAA@XZ; arrow::util::ArrowLog::~ArrowLog(void)
0x1800dda9f  mov     eax, 4
0x1800ddaa4  add     rsp, 40h
0x1800ddaa8  pop     rbx
0x1800ddaa9  retn
0x1800ddaaa  mov     eax, ebx
0x1800ddaac  add     rsp, 40h
0x1800ddab0  pop     rbx
0x1800ddab1  retn
```
