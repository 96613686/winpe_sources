# Threadpool::Initialize(void)

- ea: `0x18001f2d4`
- end: `0x18001f3bb`
- name: `?Initialize@Threadpool@@AEAAJXZ`
- size: `231`
- prototype: `int __fastcall(Threadpool *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f224`

## callees

- `0x18001f2d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f339`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f339`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f388`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18001f32a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18001f32a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001f376`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001f376`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001f36b`

## string_xrefs

- `0x18001f35d`: `Threadpool::Initialize`

## pseudocode

```c
int __fastcall Threadpool::Initialize(Threadpool *this)
{
  PTP_POOL Threadpool; // rax
  signed int LastError; // eax
  int v4; // r8d
  int result; // eax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  PTP_CLEANUP_GROUP v7; // rcx

  *(_DWORD *)this = 3;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_DWORD *)this + 15) = 1;
  *((_DWORD *)this + 16) = 72;
  Threadpool = CreateThreadpool(0);
  *((_QWORD *)this + 9) = Threadpool;
  if ( !Threadpool )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v4 = 40;
    return ZTraceReportOrigination(LastError, "Threadpool::Initialize", v4, this);
  }
  *((_QWORD *)this + 1) = Threadpool;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)this + 10) = ThreadpoolCleanupGroup;
  v7 = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v4 = 45;
    return ZTraceReportOrigination(LastError, "Threadpool::Initialize", v4, this);
  }
  result = 0;
  *((_QWORD *)this + 2) = v7;
  *((_QWORD *)this + 3) = 0;
  return result;
}

```

## disassembly

```asm
0x18001f2d4  push    rbx
0x18001f2d6  sub     rsp, 20h
0x18001f2da  mov     rbx, rcx
0x18001f2dd  mov     dword ptr [rcx], 3
0x18001f2e3  mov     qword ptr [rcx+8], 0
0x18001f2eb  mov     qword ptr [rcx+10h], 0
0x18001f2f3  mov     qword ptr [rcx+18h], 0
0x18001f2fb  mov     qword ptr [rcx+20h], 0
0x18001f303  mov     qword ptr [rcx+28h], 0
0x18001f30b  mov     qword ptr [rcx+30h], 0
0x18001f313  mov     dword ptr [rcx+38h], 0
0x18001f31a  mov     dword ptr [rcx+3Ch], 1
0x18001f321  mov     dword ptr [rcx+40h], 48h ; 'H'
0x18001f328  xor     ecx, ecx; reserved
0x18001f32a  call    cs:__imp_CreateThreadpool
0x18001f330  mov     [rbx+48h], rax
0x18001f334  test    rax, rax
0x18001f337  jnz     short loc_18001F372
0x18001f339  call    cs:__imp_GetLastError
0x18001f33f  test    eax, eax
0x18001f341  jz      short loc_18001F34F
0x18001f343  jle     short loc_18001F354
0x18001f345  movzx   eax, ax
0x18001f348  or      eax, 80070000h
0x18001f34d  jmp     short loc_18001F354
0x18001f34f  mov     eax, 80390004h
0x18001f354  mov     r8d, 28h ; '('
0x18001f35a  mov     r9, rbx
0x18001f35d  lea     rdx, aThreadpoolInit; "Threadpool::Initialize"
0x18001f364  mov     ecx, eax
0x18001f366  add     rsp, 20h
0x18001f36a  pop     rbx
0x18001f36b  jmp     cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001f372  mov     [rbx+8], rax
0x18001f376  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18001f37c  mov     [rbx+50h], rax
0x18001f380  mov     rcx, rax
0x18001f383  test    rax, rax
0x18001f386  jnz     short loc_18001F3AB
0x18001f388  call    cs:__imp_GetLastError
0x18001f38e  test    eax, eax
0x18001f390  jz      short loc_18001F39E
0x18001f392  jle     short loc_18001F3A3
0x18001f394  movzx   eax, ax
0x18001f397  or      eax, 80070000h
0x18001f39c  jmp     short loc_18001F3A3
0x18001f39e  mov     eax, 80390004h
0x18001f3a3  mov     r8d, 2Dh ; '-'
0x18001f3a9  jmp     short loc_18001F35A
0x18001f3ab  xor     eax, eax
0x18001f3ad  mov     [rbx+10h], rcx
0x18001f3b1  mov     [rbx+18h], rax
0x18001f3b5  add     rsp, 20h
0x18001f3b9  pop     rbx
0x18001f3ba  retn
```
