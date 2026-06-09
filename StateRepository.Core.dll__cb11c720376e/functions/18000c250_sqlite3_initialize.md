# sqlite3_initialize

- ea: `0x18000c250`
- end: `0x18000c42d`
- name: `sqlite3_initialize`
- size: `477`
- prototype: `__int64(void)`
- caller_count: `27`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x180001110`
- `0x180001160`
- `0x180001fbc`
- `0x1800043a0`
- `0x180004440`
- `0x180004954`
- `0x180005b90`
- `0x180005bc0`
- `0x18000c0f0`
- `0x18004a310`
- `0x180057a00`
- `0x180059420`
- `0x18005a750`
- `0x180067830`
- `0x18008bc00`
- `0x18008d6f0`
- `0x18008ec70`
- `0x18008f050`
- `0x18008f300`
- `0x18008fc50`
- `0x180091130`
- `0x180091190`
- `0x180091250`
- `0x180091300`
- `0x180091350`
- `0x1800913b0`
- `0x180091400`

## callees

- `0x180004440`
- `0x180005c78`
- `0x180005d14`
- `0x180005d40`
- `0x180009f00`
- `0x18000aac0`
- `0x18000b220`
- `0x18000c250`
- `0x18004a310`
- `0x18005c7f4`
- `0x18005dac0`
- `0x18006910e`
- `0x180085254`
- `0x1800856c0`
- `0x180086af0`
- `0x18009a010`

## pseudocode

```c
__int64 sqlite3_initialize()
{
  __int64 result; // rax
  unsigned int v1; // ebx
  __int64 v2; // rdi
  __int64 v3; // rax
  __int64 (__fastcall *v4)(_QWORD); // rax
  __int64 v5; // rax

  if ( dword_1800B5784 )
    return 0;
  result = sqlite3MutexInit();
  v1 = result;
  if ( !(_DWORD)result )
  {
    v2 = sqlite3MutexAlloc(2);
    sqlite3_mutex_enter(v2);
    dword_1800B578C = 1;
    if ( dword_1800B5790 || (v1 = sqlite3MallocInit()) == 0 )
    {
      dword_1800B5790 = 1;
      if ( qword_1800B57A0 || (v3 = sqlite3MutexAlloc(1), qword_1800B57A0 = v3, !(_BYTE)word_1800B5634) || v3 )
        ++dword_1800B5798;
      else
        v1 = 7;
    }
    sqlite3_mutex_leave(v2);
    if ( !v1 )
    {
      sqlite3_mutex_enter(qword_1800B57A0);
      if ( !dword_1800B5784 && !dword_1800B5788 )
      {
        dword_1800B5788 = 1;
        memset_0(qword_1800B5D10, 0, 0xB8u);
        sqlite3RegisterBuiltinFunctions();
        if ( dword_1800B5794 )
          goto LABEL_18;
        v4 = (__int64 (__fastcall *)(_QWORD))xmmword_1800B56E8;
        if ( !(_QWORD)xmmword_1800B56E8 )
        {
          sqlite3_config(18, qword_18009B2F0);
          v4 = (__int64 (__fastcall *)(_QWORD))xmmword_1800B56E8;
        }
        v1 = v4(*((_QWORD *)&xmmword_1800B56D8 + 1));
        if ( !v1 )
        {
LABEL_18:
          dword_1800B5794 = 1;
          v5 = sqlite3_malloc(10);
          if ( v5 )
          {
            sqlite3_free(v5);
            v1 = sqlite3_os_init();
            if ( !v1 )
            {
              v1 = sqlite3MemdbInit();
              if ( !v1 )
              {
                sqlite3PCacheBufferSetup(qword_1800B5768, (unsigned int)dword_1800B5770, (unsigned int)dword_1800B5774);
                dword_1800B5784 = 1;
              }
            }
          }
          else
          {
            v1 = 7;
          }
        }
        dword_1800B5788 = 0;
      }
      sqlite3_mutex_leave(qword_1800B57A0);
      sqlite3_mutex_enter(v2);
      if ( --dword_1800B5798 <= 0 )
      {
        sqlite3_mutex_free(qword_1800B57A0);
        qword_1800B57A0 = 0;
      }
      sqlite3_mutex_leave(v2);
    }
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x18000c250  mov     [rsp+arg_0], rbx
0x18000c255  mov     [rsp+arg_8], rbp
0x18000c25a  push    rdi
0x18000c25b  sub     rsp, 20h
0x18000c25f  cmp     cs:dword_1800B5784, 0
0x18000c266  jz      short loc_18000C270
0x18000c268  nop
0x18000c269  xor     eax, eax
0x18000c26b  jmp     loc_18000C41D
0x18000c270  call    sqlite3MutexInit
0x18000c275  mov     ebx, eax
0x18000c277  test    eax, eax
0x18000c279  jnz     loc_18000C41D
0x18000c27f  lea     ecx, [rax+2]
0x18000c282  call    sqlite3MutexAlloc
0x18000c287  mov     rcx, rax
0x18000c28a  mov     rdi, rax
0x18000c28d  call    sqlite3_mutex_enter
0x18000c292  cmp     cs:dword_1800B5790, ebx
0x18000c298  lea     ebp, [rbx+1]
0x18000c29b  mov     cs:dword_1800B578C, ebp
0x18000c2a1  jnz     short loc_18000C2AE
0x18000c2a3  call    sqlite3MallocInit
0x18000c2a8  mov     ebx, eax
0x18000c2aa  test    eax, eax
0x18000c2ac  jnz     short loc_18000C2E5
0x18000c2ae  cmp     cs:qword_1800B57A0, 0
0x18000c2b6  mov     cs:dword_1800B5790, ebp
0x18000c2bc  jnz     short loc_18000C2DF
0x18000c2be  mov     ecx, ebp
0x18000c2c0  call    sqlite3MutexAlloc
0x18000c2c5  cmp     byte ptr cs:word_1800B5634, 0
0x18000c2cc  mov     cs:qword_1800B57A0, rax
0x18000c2d3  jz      short loc_18000C2DF
0x18000c2d5  test    rax, rax
0x18000c2d8  jnz     short loc_18000C2DF
0x18000c2da  lea     ebx, [rax+7]
0x18000c2dd  jmp     short loc_18000C2E5
0x18000c2df  add     cs:dword_1800B5798, ebp
0x18000c2e5  mov     rcx, rdi
0x18000c2e8  call    sqlite3_mutex_leave
0x18000c2ed  test    ebx, ebx
0x18000c2ef  jnz     loc_18000C41B
0x18000c2f5  mov     rcx, cs:qword_1800B57A0
0x18000c2fc  call    sqlite3_mutex_enter
0x18000c301  cmp     cs:dword_1800B5784, ebx
0x18000c307  jnz     loc_18000C3D6
0x18000c30d  cmp     cs:dword_1800B5788, ebx
0x18000c313  jnz     loc_18000C3D6
0x18000c319  xor     edx, edx; Val
0x18000c31b  mov     cs:dword_1800B5788, ebp
0x18000c321  mov     r8d, 0B8h; Size
0x18000c327  lea     rcx, qword_1800B5D10; void *
0x18000c32e  call    memset_0
0x18000c333  call    sqlite3RegisterBuiltinFunctions
0x18000c338  cmp     cs:dword_1800B5794, ebx
0x18000c33e  jnz     short loc_18000C374
0x18000c340  mov     rax, qword ptr cs:xmmword_1800B56E8
0x18000c347  test    rax, rax
0x18000c34a  jnz     short loc_18000C362
0x18000c34c  lea     rdx, qword_18009B2F0
0x18000c353  lea     ecx, [rbx+12h]
0x18000c356  call    sqlite3_config
0x18000c35b  mov     rax, qword ptr cs:xmmword_1800B56E8
0x18000c362  mov     rcx, qword ptr cs:xmmword_1800B56D8+8
0x18000c369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c36e  mov     ebx, eax
0x18000c370  test    eax, eax
0x18000c372  jnz     short loc_18000C3CC
0x18000c374  mov     ecx, 0Ah
0x18000c379  mov     cs:dword_1800B5794, ebp
0x18000c37f  call    sqlite3_malloc
0x18000c384  test    rax, rax
0x18000c387  jnz     short loc_18000C38E
0x18000c389  lea     ebx, [rax+7]
0x18000c38c  jmp     short loc_18000C3CC
0x18000c38e  mov     rcx, rax
0x18000c391  call    sqlite3_free
0x18000c396  call    sqlite3_os_init
0x18000c39b  mov     ebx, eax
0x18000c39d  test    eax, eax
0x18000c39f  jnz     short loc_18000C3CC
0x18000c3a1  call    sqlite3MemdbInit
0x18000c3a6  mov     ebx, eax
0x18000c3a8  test    eax, eax
0x18000c3aa  jnz     short loc_18000C3CC
0x18000c3ac  mov     r8d, cs:dword_1800B5774
0x18000c3b3  mov     edx, cs:dword_1800B5770
0x18000c3b9  mov     rcx, cs:qword_1800B5768
0x18000c3c0  call    sqlite3PCacheBufferSetup
0x18000c3c5  nop
0x18000c3c6  mov     cs:dword_1800B5784, ebp
0x18000c3cc  mov     cs:dword_1800B5788, 0
0x18000c3d6  mov     rcx, cs:qword_1800B57A0
0x18000c3dd  call    sqlite3_mutex_leave
0x18000c3e2  mov     rcx, rdi
0x18000c3e5  call    sqlite3_mutex_enter
0x18000c3ea  mov     eax, cs:dword_1800B5798
0x18000c3f0  sub     eax, ebp
0x18000c3f2  mov     cs:dword_1800B5798, eax
0x18000c3f8  test    eax, eax
0x18000c3fa  jg      short loc_18000C413
0x18000c3fc  mov     rcx, cs:qword_1800B57A0
0x18000c403  call    sqlite3_mutex_free
0x18000c408  mov     cs:qword_1800B57A0, 0
0x18000c413  mov     rcx, rdi
0x18000c416  call    sqlite3_mutex_leave
0x18000c41b  mov     eax, ebx
0x18000c41d  mov     rbx, [rsp+28h+arg_0]
0x18000c422  mov     rbp, [rsp+28h+arg_8]
0x18000c427  add     rsp, 20h
0x18000c42b  pop     rdi
0x18000c42c  retn
```
