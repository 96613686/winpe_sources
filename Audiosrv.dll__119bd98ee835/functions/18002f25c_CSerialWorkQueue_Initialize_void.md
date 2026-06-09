# CSerialWorkQueue::Initialize(void)

- ea: `0x18002f25c`
- end: `0x18002f32f`
- name: `?Initialize@CSerialWorkQueue@@AEAAJXZ`
- size: `211`
- prototype: `__int64 __fastcall(CSerialWorkQueue *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002f0fc`

## callees

- `0x18002f25c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2ec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002f271`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002f271`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002f2aa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002f2aa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002f287`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002f287`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002f30d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002f30d`

## pseudocode

```c
__int64 __fastcall CSerialWorkQueue::Initialize(PTP_POOL *this)
{
  PTP_POOL Threadpool; // rax
  signed int v3; // eax
  signed int v4; // ebx
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  signed int LastError; // eax
  signed int v8; // eax

  if ( *this )
  {
    return 0;
  }
  else
  {
    Threadpool = CreateThreadpool(0);
    *this = Threadpool;
    if ( Threadpool )
      goto LABEL_6;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_6:
      if ( SetThreadpoolThreadMinimum(*this, 1u) )
        goto LABEL_7;
      v3 = GetLastError();
      v4 = v3;
      if ( v3 > 0 )
        v4 = (unsigned __int16)v3 | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_7:
        ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
        this[21] = ThreadpoolCleanupGroup;
        if ( ThreadpoolCleanupGroup )
        {
          v4 = 0;
LABEL_18:
          SetThreadpoolThreadMaximum(*this, 1u);
          this[2] = *this;
          this[3] = this[21];
          this[4] = 0;
          return (unsigned int)v4;
        }
        v8 = GetLastError();
        v4 = v8;
        if ( v8 > 0 )
          v4 = (unsigned __int16)v8 | 0x80070000;
        if ( v4 >= 0 )
          goto LABEL_18;
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002f25c  mov     [rsp+arg_0], rbx
0x18002f261  push    rdi
0x18002f262  sub     rsp, 20h
0x18002f266  cmp     qword ptr [rcx], 0
0x18002f26a  mov     rdi, rcx
0x18002f26d  jnz     short loc_18002F2C0
0x18002f26f  xor     ecx, ecx; reserved
0x18002f271  call    cs:__imp_CreateThreadpool
0x18002f277  mov     [rdi], rax
0x18002f27a  test    rax, rax
0x18002f27d  jz      short loc_18002F2D5
0x18002f27f  mov     rcx, [rdi]; ptpp
0x18002f282  mov     edx, 1; cthrdMic
0x18002f287  call    cs:__imp_SetThreadpoolThreadMinimum
0x18002f28d  test    eax, eax
0x18002f28f  jnz     short loc_18002F2AA
0x18002f291  call    cs:__imp_GetLastError
0x18002f297  mov     ebx, eax
0x18002f299  test    eax, eax
0x18002f29b  jle     short loc_18002F2A6
0x18002f29d  movzx   ebx, ax
0x18002f2a0  or      ebx, 80070000h
0x18002f2a6  test    ebx, ebx
0x18002f2a8  js      short loc_18002F2C2
0x18002f2aa  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18002f2b0  mov     [rdi+0A8h], rax
0x18002f2b7  test    rax, rax
0x18002f2ba  jz      short loc_18002F2EC
0x18002f2bc  xor     ebx, ebx
0x18002f2be  jmp     short loc_18002F305
0x18002f2c0  xor     ebx, ebx
0x18002f2c2  mov     eax, ebx
0x18002f2c4  mov     rbx, [rsp+28h+arg_0]
0x18002f2c9  add     rsp, 20h
0x18002f2cd  pop     rdi
0x18002f2ce  retn
0x18002f2cf  test    ebx, ebx
0x18002f2d1  js      short loc_18002F2C2
0x18002f2d3  jmp     short loc_18002F27F
0x18002f2d5  call    cs:__imp_GetLastError
0x18002f2db  mov     ebx, eax
0x18002f2dd  test    eax, eax
0x18002f2df  jle     short loc_18002F2CF
0x18002f2e1  movzx   ebx, ax
0x18002f2e4  or      ebx, 80070000h
0x18002f2ea  jmp     short loc_18002F2CF
0x18002f2ec  call    cs:__imp_GetLastError
0x18002f2f2  mov     ebx, eax
0x18002f2f4  test    eax, eax
0x18002f2f6  jle     short loc_18002F301
0x18002f2f8  movzx   ebx, ax
0x18002f2fb  or      ebx, 80070000h
0x18002f301  test    ebx, ebx
0x18002f303  js      short loc_18002F2C2
0x18002f305  mov     rcx, [rdi]; ptpp
0x18002f308  mov     edx, 1; cthrdMost
0x18002f30d  call    cs:__imp_SetThreadpoolThreadMaximum
0x18002f313  mov     rcx, [rdi]
0x18002f316  mov     [rdi+10h], rcx
0x18002f31a  mov     rcx, [rdi+0A8h]
0x18002f321  mov     [rdi+18h], rcx
0x18002f325  mov     qword ptr [rdi+20h], 0
0x18002f32d  jmp     short loc_18002F2C2
```
