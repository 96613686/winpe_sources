# DoTraceMessage(int,char const *,...)

- ea: `0x14000985c`
- end: `0x1400099de`
- name: `?DoTraceMessage@@YAXHPEBDZZ`
- size: `386`
- prototype: `void(int, const char *, ...)`
- caller_count: `24`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140009698`
- `0x14000c5f0`
- `0x14000c948`
- `0x14000cd18`
- `0x14000d5a4`
- `0x14000d890`
- `0x14000dd4c`
- `0x14000df48`
- `0x14000e144`
- `0x14000e4c8`
- `0x14000e8d8`
- `0x14000ea08`
- `0x14000ee60`
- `0x14000f280`
- `0x14000f4d4`
- `0x14000f560`
- `0x14000f6ec`
- `0x14000f920`
- `0x14000fafc`
- `0x1400104b0`
- `0x140011eac`
- `0x1400125f0`
- `0x140012998`
- `0x140012b68`

## callees

- `0x140002600`
- `0x1400028b8`
- `0x14000325c`
- `0x1400033c0`
- `0x140003428`
- `0x14000985c`
- `0x1400099e4`
- `0x140009aac`
- `0x140009f28`

## pseudocode

```c
void DoTraceMessage(int a1, const char *a2, ...)
{
  int v3; // ebx
  int v4; // ebx
  unsigned int v5; // edi
  int v6; // ebx
  int v7; // ebx
  __int64 v8; // rbx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  char Buffer[256]; // [rsp+30h] [rbp-128h] BYREF
  va_list va; // [rsp+170h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( (unsigned int)vsnprintf(Buffer, 0xFFu, a2, va) > 0xFE )
    Buffer[255] = 0;
  v3 = a1 - 1;
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      v5 = 2;
      v6 = v4 - 2;
      if ( v6 )
      {
        v5 = 4;
        v7 = v6 - 4;
        if ( v7 )
        {
          if ( v7 != 8 )
            return;
        }
        else
        {
          v5 = 3;
        }
      }
    }
    else
    {
      v5 = 1;
    }
  }
  else
  {
    v5 = 0;
  }
  v8 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
  if ( __TSS0__1__PSpLogger__YAPEAVCSpLogger__XZ_4HA > *(_DWORD *)(v8 + 4) )
  {
    Init_thread_header(&__TSS0__1__PSpLogger__YAPEAVCSpLogger__XZ_4HA);
    v9 = __TSS0__1__PSpLogger__YAPEAVCSpLogger__XZ_4HA;
    if ( __TSS0__1__PSpLogger__YAPEAVCSpLogger__XZ_4HA == -1 )
    {
      if ( CSpLogger::IsEtwEnabled() )
        McGenEventRegister_EventRegister(v10);
      atexit(`PSpLogger'::`2'::`dynamic atexit destructor for 'logger'');
      Init_thread_footer(&__TSS0__1__PSpLogger__YAPEAVCSpLogger__XZ_4HA);
      v9 = __TSS0__1__PSpLogger__YAPEAVCSpLogger__XZ_4HA;
    }
    if ( v9 > *(_DWORD *)(v8 + 4) )
    {
      Init_thread_header(&__TSS0__1__PSpLogger__YAPEAVCSpLogger__XZ_4HA);
      if ( __TSS0__1__PSpLogger__YAPEAVCSpLogger__XZ_4HA == -1 )
      {
        if ( CSpLogger::IsEtwEnabled() )
          McGenEventRegister_EventRegister(v11);
        atexit(`PSpLogger'::`2'::`dynamic atexit destructor for 'logger'');
        Init_thread_footer(&__TSS0__1__PSpLogger__YAPEAVCSpLogger__XZ_4HA);
      }
    }
  }
  CSpLogger::TraceMessage(1, v5, L"%S", Buffer, 0);
}

```

## disassembly

```asm
0x14000985c  mov     r11, rsp
0x14000985f  mov     [r11+10h], rdx
0x140009863  mov     [r11+18h], r8
0x140009867  mov     [r11+20h], r9
0x14000986b  push    rbx
0x14000986c  push    rdi
0x14000986d  push    r14
0x14000986f  sub     rsp, 140h
0x140009876  mov     rax, cs:__security_cookie
0x14000987d  xor     rax, rsp
0x140009880  mov     [rsp+158h+var_28], rax
0x140009888  mov     ebx, ecx
0x14000988a  mov     [rsp+158h+var_138], 0
0x140009893  mov     r8, rdx; Format
0x140009896  lea     r9, [r11+18h]; ArgList
0x14000989a  mov     edi, 0FFh
0x14000989f  lea     rcx, [rsp+158h+Buffer]; Buffer
0x1400098a4  mov     edx, edi; BufferCount
0x1400098a6  call    _vsnprintf
0x1400098ab  test    eax, eax
0x1400098ad  js      short loc_1400098B3
0x1400098af  cmp     eax, edi
0x1400098b1  jb      short loc_1400098BB
0x1400098b3  mov     [rsp+158h+var_29], 0
0x1400098bb  sub     ebx, 1
0x1400098be  jz      short loc_1400098EC
0x1400098c0  sub     ebx, 1
0x1400098c3  jz      short loc_1400098E5
0x1400098c5  mov     edi, 2
0x1400098ca  sub     ebx, edi
0x1400098cc  jz      short loc_1400098EE
0x1400098ce  mov     edi, 4
0x1400098d3  sub     ebx, edi
0x1400098d5  jz      short loc_1400098DE
0x1400098d7  cmp     ebx, 8
0x1400098da  jnz     short loc_140009930
0x1400098dc  jmp     short loc_1400098EE
0x1400098de  mov     edi, 3
0x1400098e3  jmp     short loc_1400098EE
0x1400098e5  mov     edi, 1
0x1400098ea  jmp     short loc_1400098EE
0x1400098ec  xor     edi, edi
0x1400098ee  mov     rax, gs:58h
0x1400098f7  mov     r14d, 4
0x1400098fd  mov     rbx, [rax]
0x140009900  mov     eax, cs:?$TSS0@?1??PSpLogger@@YAPEAVCSpLogger@@XZ@4HA
0x140009906  cmp     eax, [r14+rbx]
0x14000990a  jg      short loc_140009966
0x14000990c  jmp     short loc_140009918
0x14000990e  cmp     eax, [r14+rbx]
0x140009912  jg      loc_1400099AE
0x140009918  lea     r9, [rsp+158h+Buffer]
0x14000991d  mov     edx, edi
0x14000991f  lea     r8, aS_2; "%S"
0x140009926  mov     ecx, 1
0x14000992b  call    ?TraceMessage@CSpLogger@@SAXW4SPLOG_SOURCE@@W4SPLOG_LEVEL@@PEBGZZ; CSpLogger::TraceMessage(SPLOG_SOURCE,SPLOG_LEVEL,ushort const *,...)
0x140009930  mov     rcx, [rsp+158h+var_28]
0x140009938  xor     rcx, rsp; StackCookie
0x14000993b  call    __security_check_cookie
0x140009940  add     rsp, 140h
0x140009947  pop     r14
0x140009949  pop     rdi
0x14000994a  pop     rbx
0x14000994b  retn
0x14000994c  lea     rcx, ??__Flogger@?1??PSpLogger@@YAPEAVCSpLogger@@XZ@YAXXZ; void (__cdecl *)()
0x140009953  call    atexit
0x140009958  lea     rcx, ?$TSS0@?1??PSpLogger@@YAPEAVCSpLogger@@XZ@4HA
0x14000995f  call    _Init_thread_footer
0x140009964  jmp     short loc_140009918
0x140009966  lea     rcx, ?$TSS0@?1??PSpLogger@@YAPEAVCSpLogger@@XZ@4HA
0x14000996d  call    _Init_thread_header
0x140009972  mov     eax, cs:?$TSS0@?1??PSpLogger@@YAPEAVCSpLogger@@XZ@4HA
0x140009978  cmp     eax, 0FFFFFFFFh
0x14000997b  jnz     short loc_14000990E
0x14000997d  call    ?IsEtwEnabled@CSpLogger@@SA_NXZ; CSpLogger::IsEtwEnabled(void)
0x140009982  test    al, al
0x140009984  jz      short loc_14000998B
0x140009986  call    McGenEventRegister_EventRegister
0x14000998b  lea     rcx, ??__Flogger@?1??PSpLogger@@YAPEAVCSpLogger@@XZ@YAXXZ; void (__cdecl *)()
0x140009992  call    atexit
0x140009997  lea     rcx, ?$TSS0@?1??PSpLogger@@YAPEAVCSpLogger@@XZ@4HA
0x14000999e  call    _Init_thread_footer
0x1400099a3  mov     eax, cs:?$TSS0@?1??PSpLogger@@YAPEAVCSpLogger@@XZ@4HA
0x1400099a9  jmp     loc_14000990E
0x1400099ae  lea     rcx, ?$TSS0@?1??PSpLogger@@YAPEAVCSpLogger@@XZ@4HA
0x1400099b5  call    _Init_thread_header
0x1400099ba  cmp     cs:?$TSS0@?1??PSpLogger@@YAPEAVCSpLogger@@XZ@4HA, 0FFFFFFFFh
0x1400099c1  jnz     loc_140009918
0x1400099c7  call    ?IsEtwEnabled@CSpLogger@@SA_NXZ; CSpLogger::IsEtwEnabled(void)
0x1400099cc  test    al, al
0x1400099ce  jz      loc_14000994C
0x1400099d4  call    McGenEventRegister_EventRegister
0x1400099d9  jmp     loc_14000994C
```
