# CSerialWorkQueue::Initialize(void)

- ea: `0x18003ee74`
- end: `0x18003ef4a`
- name: `?Initialize@CSerialWorkQueue@@AEAAJXZ`
- size: `214`
- prototype: `__int64 __fastcall(CSerialWorkQueue *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003f630`

## callees

- `0x18003ee74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ee9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ee9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eef8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18003ef1d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18003ef1d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18003eee6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18003eee6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18003eec3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18003eec3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18003ee90`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18003ee90`

## pseudocode

```c
__int64 __fastcall CSerialWorkQueue::Initialize(PTP_POOL *this)
{
  signed int v2; // ebx
  PTP_POOL Threadpool; // rax
  signed int LastError; // eax
  signed int v5; // eax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  signed int v7; // eax

  if ( *this )
    return 0;
  Threadpool = CreateThreadpool(0);
  *this = Threadpool;
  if ( Threadpool )
    goto LABEL_10;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_10:
    if ( SetThreadpoolThreadMinimum(*this, 1u) )
      goto LABEL_11;
    v5 = GetLastError();
    v2 = v5;
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_11:
      ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
      this[21] = ThreadpoolCleanupGroup;
      if ( ThreadpoolCleanupGroup )
      {
        v2 = 0;
LABEL_17:
        SetThreadpoolThreadMaximum(*this, 1u);
        this[2] = *this;
        this[3] = this[21];
        this[4] = 0;
        return (unsigned int)v2;
      }
      v7 = GetLastError();
      v2 = v7;
      if ( v7 > 0 )
        v2 = (unsigned __int16)v7 | 0x80070000;
      if ( v2 >= 0 )
        goto LABEL_17;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18003ee74  mov     [rsp+arg_0], rbx
0x18003ee79  push    rdi
0x18003ee7a  sub     rsp, 20h
0x18003ee7e  cmp     qword ptr [rcx], 0
0x18003ee82  mov     rdi, rcx
0x18003ee85  jz      short loc_18003EE8E
0x18003ee87  xor     ebx, ebx
0x18003ee89  jmp     loc_18003EF3D
0x18003ee8e  xor     ecx, ecx; reserved
0x18003ee90  call    cs:__imp_CreateThreadpool
0x18003ee96  mov     [rdi], rax
0x18003ee99  test    rax, rax
0x18003ee9c  jnz     short loc_18003EEBB
0x18003ee9e  call    cs:__imp_GetLastError
0x18003eea4  mov     ebx, eax
0x18003eea6  test    eax, eax
0x18003eea8  jle     short loc_18003EEB3
0x18003eeaa  movzx   ebx, ax
0x18003eead  or      ebx, 80070000h
0x18003eeb3  test    ebx, ebx
0x18003eeb5  js      loc_18003EF3D
0x18003eebb  mov     rcx, [rdi]; ptpp
0x18003eebe  mov     edx, 1; cthrdMic
0x18003eec3  call    cs:__imp_SetThreadpoolThreadMinimum
0x18003eec9  test    eax, eax
0x18003eecb  jnz     short loc_18003EEE6
0x18003eecd  call    cs:__imp_GetLastError
0x18003eed3  mov     ebx, eax
0x18003eed5  test    eax, eax
0x18003eed7  jle     short loc_18003EEE2
0x18003eed9  movzx   ebx, ax
0x18003eedc  or      ebx, 80070000h
0x18003eee2  test    ebx, ebx
0x18003eee4  js      short loc_18003EF3D
0x18003eee6  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18003eeec  mov     [rdi+0A8h], rax
0x18003eef3  test    rax, rax
0x18003eef6  jnz     short loc_18003EF13
0x18003eef8  call    cs:__imp_GetLastError
0x18003eefe  mov     ebx, eax
0x18003ef00  test    eax, eax
0x18003ef02  jle     short loc_18003EF0D
0x18003ef04  movzx   ebx, ax
0x18003ef07  or      ebx, 80070000h
0x18003ef0d  test    ebx, ebx
0x18003ef0f  js      short loc_18003EF3D
0x18003ef11  jmp     short loc_18003EF15
0x18003ef13  xor     ebx, ebx
0x18003ef15  mov     rcx, [rdi]; ptpp
0x18003ef18  mov     edx, 1; cthrdMost
0x18003ef1d  call    cs:__imp_SetThreadpoolThreadMaximum
0x18003ef23  mov     rcx, [rdi]
0x18003ef26  mov     [rdi+10h], rcx
0x18003ef2a  mov     rcx, [rdi+0A8h]
0x18003ef31  mov     [rdi+18h], rcx
0x18003ef35  mov     qword ptr [rdi+20h], 0
0x18003ef3d  mov     eax, ebx
0x18003ef3f  mov     rbx, [rsp+28h+arg_0]
0x18003ef44  add     rsp, 20h
0x18003ef48  pop     rdi
0x18003ef49  retn
```
