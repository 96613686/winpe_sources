# CSerialWorkQueue::Initialize(void)

- ea: `0x14000f1a4`
- end: `0x14000f28b`
- name: `?Initialize@CSerialWorkQueue@@AEAAJXZ`
- size: `231`
- prototype: `__int64 __fastcall(CSerialWorkQueue *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ec10`
- `0x14000efc8`
- `0x140058c50`

## callees

- `0x14000f1a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f25a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f271`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f25a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f271`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x14000f1ec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x14000f1ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x14000f20e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x14000f20e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x14000f1e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x14000f1e2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x14000f1c8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x14000f1c8`

## pseudocode

```c
__int64 __fastcall CSerialWorkQueue::Initialize(PTP_POOL *this)
{
  signed int v2; // ebx
  PTP_POOL Threadpool; // rax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  signed int v6; // eax
  signed int LastError; // eax
  signed int v8; // eax

  if ( *this )
    return 0;
  Threadpool = CreateThreadpool(0);
  *this = Threadpool;
  if ( Threadpool )
    goto LABEL_12;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_12:
    if ( SetThreadpoolThreadMinimum(*this, 1u) )
      goto LABEL_6;
    v6 = GetLastError();
    v2 = v6;
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_6:
      ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
      this[21] = ThreadpoolCleanupGroup;
      if ( ThreadpoolCleanupGroup )
      {
        v2 = 0;
LABEL_9:
        SetThreadpoolThreadMaximum(*this, 1u);
        this[2] = *this;
        this[3] = this[21];
        this[4] = 0;
        return (unsigned int)v2;
      }
      v8 = GetLastError();
      v2 = v8;
      if ( v8 > 0 )
        v2 = (unsigned __int16)v8 | 0x80070000;
      if ( v2 >= 0 )
        goto LABEL_9;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000f1a4  mov     [rsp+arg_0], rbx
0x14000f1a9  push    rdi
0x14000f1aa  sub     rsp, 20h
0x14000f1ae  cmp     qword ptr [rcx], 0
0x14000f1b2  mov     rdi, rcx
0x14000f1b5  jz      short loc_14000F1C6
0x14000f1b7  xor     ebx, ebx
0x14000f1b9  mov     eax, ebx
0x14000f1bb  mov     rbx, [rsp+28h+arg_0]
0x14000f1c0  add     rsp, 20h
0x14000f1c4  pop     rdi
0x14000f1c5  retn
0x14000f1c6  xor     ecx, ecx; reserved
0x14000f1c8  call    cs:__imp_CreateThreadpool
0x14000f1ce  mov     [rdi], rax
0x14000f1d1  test    rax, rax
0x14000f1d4  jz      loc_14000F25A
0x14000f1da  mov     rcx, [rdi]; ptpp
0x14000f1dd  mov     edx, 1; cthrdMic
0x14000f1e2  call    cs:__imp_SetThreadpoolThreadMinimum
0x14000f1e8  test    eax, eax
0x14000f1ea  jz      short loc_14000F230
0x14000f1ec  call    cs:__imp_CreateThreadpoolCleanupGroup
0x14000f1f2  mov     [rdi+0A8h], rax
0x14000f1f9  test    rax, rax
0x14000f1fc  jz      short loc_14000F271
0x14000f1fe  xor     ebx, ebx
0x14000f200  jmp     short loc_14000F206
0x14000f202  test    ebx, ebx
0x14000f204  js      short loc_14000F1B9
0x14000f206  mov     rcx, [rdi]; ptpp
0x14000f209  mov     edx, 1; cthrdMost
0x14000f20e  call    cs:__imp_SetThreadpoolThreadMaximum
0x14000f214  mov     rcx, [rdi]
0x14000f217  mov     [rdi+10h], rcx
0x14000f21b  mov     rcx, [rdi+0A8h]
0x14000f222  mov     [rdi+18h], rcx
0x14000f226  mov     qword ptr [rdi+20h], 0
0x14000f22e  jmp     short loc_14000F1B9
0x14000f230  call    cs:__imp_GetLastError
0x14000f236  mov     ebx, eax
0x14000f238  test    eax, eax
0x14000f23a  jg      short loc_14000F246
0x14000f23c  test    ebx, ebx
0x14000f23e  js      loc_14000F1B9
0x14000f244  jmp     short loc_14000F1EC
0x14000f246  movzx   ebx, ax
0x14000f249  or      ebx, 80070000h
0x14000f24f  jmp     short loc_14000F23C
0x14000f251  test    ebx, ebx
0x14000f253  jns     short loc_14000F1DA
0x14000f255  jmp     loc_14000F1B9
0x14000f25a  call    cs:__imp_GetLastError
0x14000f260  mov     ebx, eax
0x14000f262  test    eax, eax
0x14000f264  jle     short loc_14000F251
0x14000f266  movzx   ebx, ax
0x14000f269  or      ebx, 80070000h
0x14000f26f  jmp     short loc_14000F251
0x14000f271  call    cs:__imp_GetLastError
0x14000f277  mov     ebx, eax
0x14000f279  test    eax, eax
0x14000f27b  jle     short loc_14000F202
0x14000f27d  movzx   ebx, ax
0x14000f280  or      ebx, 80070000h
0x14000f286  jmp     loc_14000F202
```
