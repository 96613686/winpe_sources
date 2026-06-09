# CSerialWorkQueue::Initialize(void)

- ea: `0x18002f0fc`
- end: `0x18002f1cf`
- name: `?Initialize@CSerialWorkQueue@@AEAAJXZ`
- size: `211`
- prototype: `__int64 __fastcall(CSerialWorkQueue *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ef9c`

## callees

- `0x18002f0fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f175`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f18c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f175`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f18c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002f111`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002f111`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002f14a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002f14a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002f127`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002f127`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002f1ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002f1ad`

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
0x18002f0fc  mov     [rsp+arg_0], rbx
0x18002f101  push    rdi
0x18002f102  sub     rsp, 20h
0x18002f106  cmp     qword ptr [rcx], 0
0x18002f10a  mov     rdi, rcx
0x18002f10d  jnz     short loc_18002F160
0x18002f10f  xor     ecx, ecx; reserved
0x18002f111  call    cs:__imp_CreateThreadpool
0x18002f117  mov     [rdi], rax
0x18002f11a  test    rax, rax
0x18002f11d  jz      short loc_18002F175
0x18002f11f  mov     rcx, [rdi]; ptpp
0x18002f122  mov     edx, 1; cthrdMic
0x18002f127  call    cs:__imp_SetThreadpoolThreadMinimum
0x18002f12d  test    eax, eax
0x18002f12f  jnz     short loc_18002F14A
0x18002f131  call    cs:__imp_GetLastError
0x18002f137  mov     ebx, eax
0x18002f139  test    eax, eax
0x18002f13b  jle     short loc_18002F146
0x18002f13d  movzx   ebx, ax
0x18002f140  or      ebx, 80070000h
0x18002f146  test    ebx, ebx
0x18002f148  js      short loc_18002F162
0x18002f14a  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18002f150  mov     [rdi+0A8h], rax
0x18002f157  test    rax, rax
0x18002f15a  jz      short loc_18002F18C
0x18002f15c  xor     ebx, ebx
0x18002f15e  jmp     short loc_18002F1A5
0x18002f160  xor     ebx, ebx
0x18002f162  mov     eax, ebx
0x18002f164  mov     rbx, [rsp+28h+arg_0]
0x18002f169  add     rsp, 20h
0x18002f16d  pop     rdi
0x18002f16e  retn
0x18002f16f  test    ebx, ebx
0x18002f171  js      short loc_18002F162
0x18002f173  jmp     short loc_18002F11F
0x18002f175  call    cs:__imp_GetLastError
0x18002f17b  mov     ebx, eax
0x18002f17d  test    eax, eax
0x18002f17f  jle     short loc_18002F16F
0x18002f181  movzx   ebx, ax
0x18002f184  or      ebx, 80070000h
0x18002f18a  jmp     short loc_18002F16F
0x18002f18c  call    cs:__imp_GetLastError
0x18002f192  mov     ebx, eax
0x18002f194  test    eax, eax
0x18002f196  jle     short loc_18002F1A1
0x18002f198  movzx   ebx, ax
0x18002f19b  or      ebx, 80070000h
0x18002f1a1  test    ebx, ebx
0x18002f1a3  js      short loc_18002F162
0x18002f1a5  mov     rcx, [rdi]; ptpp
0x18002f1a8  mov     edx, 1; cthrdMost
0x18002f1ad  call    cs:__imp_SetThreadpoolThreadMaximum
0x18002f1b3  mov     rcx, [rdi]
0x18002f1b6  mov     [rdi+10h], rcx
0x18002f1ba  mov     rcx, [rdi+0A8h]
0x18002f1c1  mov     [rdi+18h], rcx
0x18002f1c5  mov     qword ptr [rdi+20h], 0
0x18002f1cd  jmp     short loc_18002F162
```
