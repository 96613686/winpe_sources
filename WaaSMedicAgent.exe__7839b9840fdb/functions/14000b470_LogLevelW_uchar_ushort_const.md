# LogLevelW(uchar,ushort const *,...)

- ea: `0x14000b470`
- end: `0x14000b5d6`
- name: `?LogLevelW@@YAXEPEBGZZ`
- size: `358`
- prototype: `void(unsigned __int8, const unsigned __int16 *, ...)`
- caller_count: `19`
- callee_count: `8`
- tags: ``

## callers

- `0x140007f3c`
- `0x1400093c0`
- `0x140009580`
- `0x140009c30`
- `0x14000a120`
- `0x14000a8f0`
- `0x14000f000`
- `0x14000f3ec`
- `0x14000f744`
- `0x14000fa3c`
- `0x14000ffa4`
- `0x14001002c`
- `0x1400102f0`
- `0x140010a24`
- `0x140010c94`
- `0x140010f14`
- `0x140011128`
- `0x140011244`
- `0x140011508`

## callees

- `0x14000198c`
- `0x140002a30`
- `0x1400036b4`
- `0x14000b470`
- `0x14000b614`
- `0x14000b684`
- `0x14000b6f4`
- `0x14000b764`

## pseudocode

```c
void LogLevelW(unsigned __int8 a1, const unsigned __int16 *a2, ...)
{
  int v2; // ebx
  _QWORD *ThreadLocalStoragePointer; // rax
  wchar_t *v4; // rdi
  unsigned int v5; // eax
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  unsigned int v9; // eax
  int v10; // ecx
  const unsigned __int16 *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // [rsp+38h] [rbp-29h] BYREF
  _BYTE v14[32]; // [rsp+48h] [rbp-19h] BYREF
  const unsigned __int16 *v15; // [rsp+68h] [rbp+7h]
  int v16; // [rsp+70h] [rbp+Fh]
  int v17; // [rsp+74h] [rbp+13h]
  __int64 *v18; // [rsp+78h] [rbp+17h]
  __int64 v19; // [rsp+80h] [rbp+1Fh]
  va_list Args; // [rsp+D8h] [rbp+77h] BYREF

  va_start(Args, a2);
  v2 = a1;
  if ( a1 < (unsigned int)dword_140020038 )
  {
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v13 = 0;
    v4 = (wchar_t *)(*ThreadLocalStoragePointer + 32LL);
    *v4 = 0;
    v5 = vsnwprintf(v4, 0xFFEu, a2, Args);
    if ( v5 > 0xFFE )
    {
      v9 = dword_140020038;
      v10 = 2;
      v4[4094] = 0;
      if ( v9 > 2 )
      {
        v11 = a2;
        v18 = &v13;
        v19 = 4;
        LODWORD(v13) = -2147024774;
        if ( a2 )
        {
          v12 = -1;
          do
            ++v12;
          while ( a2[v12] );
          v10 = 2 * v12 + 2;
        }
        else
        {
          v11 = &dword_1400158BC;
        }
        v15 = v11;
        v16 = v10;
        v17 = 0;
        tlgWriteTransfer_EventWriteTransfer(&dword_140020038, &word_140019E96, 0, 0, 4, v14);
      }
    }
    else
    {
      if ( v5 == 4094 )
        v4[4094] = 0;
      v6 = v2 - 2;
      if ( v6 )
      {
        v7 = v6 - 1;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
          {
            if ( v8 == 1 )
              _LogMsgVerboseW(v4);
          }
          else
          {
            _LogMsgInfoW(v4);
          }
        }
        else
        {
          _LogMsgWarningW(v4);
        }
      }
      else
      {
        _LogMsgErrorW(v4);
      }
    }
  }
}

```

## disassembly

```asm
0x14000b470  mov     rax, rsp
0x14000b473  mov     [rax+10h], rdx
0x14000b477  mov     [rax+18h], r8
0x14000b47b  mov     [rax+20h], r9
0x14000b47f  push    rbp
0x14000b480  push    rbx
0x14000b481  push    rsi
0x14000b482  push    rdi
0x14000b483  lea     rbp, [rax-5Fh]
0x14000b487  sub     rsp, 98h
0x14000b48e  mov     rax, cs:__security_cookie
0x14000b495  xor     rax, rsp
0x14000b498  mov     [rbp+57h+var_30], rax
0x14000b49c  mov     eax, cs:dword_140020038
0x14000b4a2  movzx   ebx, cl
0x14000b4a5  cmp     ebx, eax
0x14000b4a7  jnb     loc_14000B5BE
0x14000b4ad  mov     rax, gs:58h
0x14000b4b6  lea     r9, [rbp+57h+Args]; Args
0x14000b4ba  mov     r8, [rbp+57h+Format]; Format
0x14000b4be  xor     esi, esi
0x14000b4c0  mov     edi, 20h ; ' '
0x14000b4c5  mov     edx, 0FFEh; BufferCount
0x14000b4ca  mov     [rbp+57h+var_80], rsi
0x14000b4ce  add     rdi, [rax]
0x14000b4d1  mov     rcx, rdi; Buffer
0x14000b4d4  mov     [rdi], si
0x14000b4d7  call    _vsnwprintf
0x14000b4dc  test    eax, eax
0x14000b4de  js      short loc_14000B53C
0x14000b4e0  cmp     eax, 0FFEh
0x14000b4e5  ja      short loc_14000B53C
0x14000b4e7  jnz     short loc_14000B4F0
0x14000b4e9  mov     [rdi+1FFCh], si
0x14000b4f0  sub     ebx, 2
0x14000b4f3  jz      short loc_14000B52F
0x14000b4f5  sub     ebx, 1
0x14000b4f8  jz      short loc_14000B522
0x14000b4fa  sub     ebx, 1
0x14000b4fd  jz      short loc_14000B515
0x14000b4ff  cmp     ebx, 1
0x14000b502  jnz     loc_14000B5BE
0x14000b508  mov     rcx, rdi; unsigned __int16 *
0x14000b50b  call    ?_LogMsgVerboseW@@YAXPEAG@Z; _LogMsgVerboseW(ushort *)
0x14000b510  jmp     loc_14000B5BE
0x14000b515  mov     rcx, rdi; unsigned __int16 *
0x14000b518  call    ?_LogMsgInfoW@@YAXPEAG@Z; _LogMsgInfoW(ushort *)
0x14000b51d  jmp     loc_14000B5BE
0x14000b522  mov     rcx, rdi; unsigned __int16 *
0x14000b525  call    ?_LogMsgWarningW@@YAXPEAG@Z; _LogMsgWarningW(ushort *)
0x14000b52a  jmp     loc_14000B5BE
0x14000b52f  mov     rcx, rdi; unsigned __int16 *
0x14000b532  call    ?_LogMsgErrorW@@YAXPEAG@Z; _LogMsgErrorW(ushort *)
0x14000b537  jmp     loc_14000B5BE
0x14000b53c  mov     eax, cs:dword_140020038
0x14000b542  mov     ecx, 2
0x14000b547  mov     [rdi+1FFCh], si
0x14000b54e  cmp     eax, ecx
0x14000b550  jbe     short loc_14000B5BE
0x14000b552  mov     rax, [rbp+57h+Format]
0x14000b556  lea     rdx, [rbp+57h+var_80]
0x14000b55a  mov     [rbp+57h+var_40], rdx
0x14000b55e  lea     edx, [rcx+2]
0x14000b561  mov     [rbp+57h+var_38], rdx
0x14000b565  mov     dword ptr [rbp+57h+var_80], 8007007Ah
0x14000b56c  test    rax, rax
0x14000b56f  jz      short loc_14000B587
0x14000b571  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000b575  inc     rcx
0x14000b578  cmp     [rax+rcx*2], si
0x14000b57c  jnz     short loc_14000B575
0x14000b57e  lea     ecx, ds:2[rcx*2]
0x14000b585  jmp     short loc_14000B58E
0x14000b587  lea     rax, dword_1400158BC
0x14000b58e  mov     [rbp+57h+var_50], rax
0x14000b592  xor     r9d, r9d
0x14000b595  lea     rax, [rbp+57h+var_70]
0x14000b599  mov     [rbp+57h+var_48], ecx
0x14000b59c  mov     [rsp+28h], rax
0x14000b5a1  lea     rcx, dword_140020038
0x14000b5a8  mov     dword ptr [rsp+0B0h+var_90], edx
0x14000b5ac  xor     r8d, r8d
0x14000b5af  lea     rdx, word_140019E96
0x14000b5b6  mov     [rbp+57h+var_44], esi
0x14000b5b9  call    _tlgWriteTransfer_EventWriteTransfer
0x14000b5be  mov     rcx, [rbp+57h+var_30]
0x14000b5c2  xor     rcx, rsp; StackCookie
0x14000b5c5  call    __security_check_cookie
0x14000b5ca  add     rsp, 98h
0x14000b5d1  pop     rdi
0x14000b5d2  pop     rsi
0x14000b5d3  pop     rbx
0x14000b5d4  pop     rbp
0x14000b5d5  retn
```
