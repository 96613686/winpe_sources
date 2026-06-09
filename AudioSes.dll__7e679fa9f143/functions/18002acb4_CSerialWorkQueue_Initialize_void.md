# CSerialWorkQueue::Initialize(void)

- ea: `0x18002acb4`
- end: `0x18002ad91`
- name: `?Initialize@CSerialWorkQueue@@AEAAJXZ`
- size: `221`
- prototype: `__int64 __fastcall(CSerialWorkQueue *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ba58`

## callees

- `0x18002acb4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002ad26`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002ad26`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002ace7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002ace7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002accd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002accd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002ad0a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002ad0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad76`

## pseudocode

```c
__int64 __fastcall CSerialWorkQueue::Initialize(PTP_POOL *this)
{
  PTP_POOL Threadpool; // rax
  signed int v3; // eax
  signed int v4; // ebx
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  signed int v7; // eax
  signed int LastError; // eax

  if ( *this )
    return 0;
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
LABEL_9:
        SetThreadpoolThreadMaximum(*this, 1u);
        this[2] = *this;
        this[3] = this[21];
        this[4] = 0;
        return (unsigned int)v4;
      }
      v7 = GetLastError();
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      if ( v4 >= 0 )
        goto LABEL_9;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002acb4  mov     [rsp+arg_0], rbx
0x18002acb9  push    rdi
0x18002acba  sub     rsp, 20h
0x18002acbe  cmp     qword ptr [rcx], 0
0x18002acc2  mov     rdi, rcx
0x18002acc5  jnz     loc_18002AD8D
0x18002accb  xor     ecx, ecx; reserved
0x18002accd  call    cs:__imp_CreateThreadpool
0x18002acd3  mov     [rdi], rax
0x18002acd6  test    rax, rax
0x18002acd9  jz      loc_18002AD76
0x18002acdf  mov     rcx, [rdi]; ptpp
0x18002ace2  mov     edx, 1; cthrdMic
0x18002ace7  call    cs:__imp_SetThreadpoolThreadMinimum
0x18002aced  test    eax, eax
0x18002acef  jnz     short loc_18002AD0A
0x18002acf1  call    cs:__imp_GetLastError
0x18002acf7  mov     ebx, eax
0x18002acf9  test    eax, eax
0x18002acfb  jle     short loc_18002AD06
0x18002acfd  movzx   ebx, ax
0x18002ad00  or      ebx, 80070000h
0x18002ad06  test    ebx, ebx
0x18002ad08  js      short loc_18002AD4C
0x18002ad0a  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18002ad10  mov     [rdi+0A8h], rax
0x18002ad17  test    rax, rax
0x18002ad1a  jz      short loc_18002AD59
0x18002ad1c  xor     ebx, ebx
0x18002ad1e  mov     rcx, [rdi]; ptpp
0x18002ad21  mov     edx, 1; cthrdMost
0x18002ad26  call    cs:__imp_SetThreadpoolThreadMaximum
0x18002ad2c  mov     rcx, [rdi]
0x18002ad2f  mov     [rdi+10h], rcx
0x18002ad33  mov     rcx, [rdi+0A8h]
0x18002ad3a  mov     [rdi+18h], rcx
0x18002ad3e  mov     qword ptr [rdi+20h], 0
0x18002ad46  jmp     short loc_18002AD4C
0x18002ad48  test    ebx, ebx
0x18002ad4a  jns     short loc_18002ACDF
0x18002ad4c  mov     eax, ebx
0x18002ad4e  mov     rbx, [rsp+28h+arg_0]
0x18002ad53  add     rsp, 20h
0x18002ad57  pop     rdi
0x18002ad58  retn
0x18002ad59  call    cs:__imp_GetLastError
0x18002ad5f  mov     ebx, eax
0x18002ad61  test    eax, eax
0x18002ad63  jg      short loc_18002AD6B
0x18002ad65  test    ebx, ebx
0x18002ad67  js      short loc_18002AD4C
0x18002ad69  jmp     short loc_18002AD1E
0x18002ad6b  movzx   ebx, ax
0x18002ad6e  or      ebx, 80070000h
0x18002ad74  jmp     short loc_18002AD65
0x18002ad76  call    cs:__imp_GetLastError
0x18002ad7c  mov     ebx, eax
0x18002ad7e  test    eax, eax
0x18002ad80  jle     short loc_18002AD48
0x18002ad82  movzx   ebx, ax
0x18002ad85  or      ebx, 80070000h
0x18002ad8b  jmp     short loc_18002AD48
0x18002ad8d  xor     ebx, ebx
0x18002ad8f  jmp     short loc_18002AD4C
```
