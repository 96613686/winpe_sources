# LogLevel(uchar,ushort const *,...)

- ea: `0x18001752c`
- end: `0x18001769d`
- name: `?LogLevel@@YAXEPEBGZZ`
- size: `369`
- prototype: `void(unsigned __int8, const unsigned __int16 *, ...)`
- caller_count: `33`
- callee_count: `7`
- tags: ``

## callers

- `0x180006eb0`
- `0x180006f70`
- `0x180007000`
- `0x1800070d0`
- `0x180007380`
- `0x180007530`
- `0x180007670`
- `0x180007900`
- `0x180007b50`
- `0x1800083c0`
- `0x1800089d0`
- `0x180008c40`
- `0x180008e70`
- `0x180009020`
- `0x180009180`
- `0x180009990`
- `0x180009a40`
- `0x180009b60`
- `0x180009c30`
- `0x180009d40`
- `0x18000ccf0`
- `0x18000e620`
- `0x18000f728`
- `0x18000fa40`
- `0x18000faf0`
- `0x18000fb70`
- `0x18000fcd0`
- `0x18000ff20`
- `0x18000ffa0`
- `0x180010100`
- `0x1800104c0`
- `0x1800105b0`
- `0x180010630`

## callees

- `0x180001a8c`
- `0x18001752c`
- `0x180017f34`
- `0x180017fd0`
- `0x180018008`
- `0x180018040`
- `0x180019760`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18001759d`
- `msvcrt!_vsnwprintf` at `0x18001759d`

## pseudocode

```c
void LogLevel(unsigned __int8 a1, wchar_t *a2, ...)
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
  int *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // [rsp+38h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+48h] [rbp-19h] BYREF
  int *v15; // [rsp+68h] [rbp+7h]
  int v16; // [rsp+70h] [rbp+Fh]
  int v17; // [rsp+74h] [rbp+13h]
  __int64 *v18; // [rsp+78h] [rbp+17h]
  __int64 v19; // [rsp+80h] [rbp+1Fh]
  va_list Args; // [rsp+D8h] [rbp+77h] BYREF

  va_start(Args, a2);
  v2 = a1;
  if ( a1 < (unsigned int)dword_180027080 )
  {
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v13 = 0;
    v4 = (wchar_t *)(ThreadLocalStoragePointer[tls_index] + 16LL);
    *v4 = 0;
    v5 = _vsnwprintf(v4, 0xFFEu, a2, Args);
    if ( v5 > 0xFFE )
    {
      v9 = dword_180027080;
      v10 = 2;
      v4[4094] = 0;
      if ( v9 > 2 )
      {
        v11 = (int *)a2;
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
          v11 = &dword_18001D62C;
        }
        v15 = v11;
        v16 = v10;
        v17 = 0;
        tlgWriteTransfer_EventWriteTransfer(
          (__int64)&dword_180027080,
          (unsigned __int8 *)byte_180020F0B,
          0,
          0,
          4u,
          &v14);
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
              _LogMsgVerbose(v4);
          }
          else
          {
            _LogMsgInfo(v4);
          }
        }
        else
        {
          _LogMsgWarning(v4);
        }
      }
      else
      {
        _LogMsgError(v4);
      }
    }
  }
}

```

## disassembly

```asm
0x18001752c  mov     rax, rsp
0x18001752f  mov     [rax+10h], rdx
0x180017533  mov     [rax+18h], r8
0x180017537  mov     [rax+20h], r9
0x18001753b  push    rbp
0x18001753c  push    rbx
0x18001753d  push    rsi
0x18001753e  push    rdi
0x18001753f  lea     rbp, [rax-5Fh]
0x180017543  sub     rsp, 98h
0x18001754a  mov     rax, cs:__security_cookie
0x180017551  xor     rax, rsp
0x180017554  mov     [rbp+57h+var_30], rax
0x180017558  mov     eax, cs:dword_180027080
0x18001755e  movzx   ebx, cl
0x180017561  cmp     ebx, eax
0x180017563  jnb     loc_180017685
0x180017569  mov     ecx, cs:_tls_index
0x18001756f  lea     r9, [rbp+57h+Args]; Args
0x180017573  mov     rax, gs:58h
0x18001757c  xor     esi, esi
0x18001757e  mov     r8, [rbp+57h+Format]; Format
0x180017582  mov     edx, 10h
0x180017587  mov     [rbp+57h+var_80], rsi
0x18001758b  mov     rdi, [rax+rcx*8]
0x18001758f  add     rdi, rdx
0x180017592  mov     edx, 0FFEh; BufferCount
0x180017597  mov     rcx, rdi; Buffer
0x18001759a  mov     [rdi], si
0x18001759d  call    cs:__imp__vsnwprintf
0x1800175a3  test    eax, eax
0x1800175a5  js      short loc_180017603
0x1800175a7  cmp     eax, 0FFEh
0x1800175ac  ja      short loc_180017603
0x1800175ae  jnz     short loc_1800175B7
0x1800175b0  mov     [rdi+1FFCh], si
0x1800175b7  sub     ebx, 2
0x1800175ba  jz      short loc_1800175F6
0x1800175bc  sub     ebx, 1
0x1800175bf  jz      short loc_1800175E9
0x1800175c1  sub     ebx, 1
0x1800175c4  jz      short loc_1800175DC
0x1800175c6  cmp     ebx, 1
0x1800175c9  jnz     loc_180017685
0x1800175cf  mov     rcx, rdi; unsigned __int16 *
0x1800175d2  call    ?_LogMsgVerbose@@YAXPEAG@Z; _LogMsgVerbose(ushort *)
0x1800175d7  jmp     loc_180017685
0x1800175dc  mov     rcx, rdi; unsigned __int16 *
0x1800175df  call    ?_LogMsgInfo@@YAXPEAG@Z; _LogMsgInfo(ushort *)
0x1800175e4  jmp     loc_180017685
0x1800175e9  mov     rcx, rdi; unsigned __int16 *
0x1800175ec  call    ?_LogMsgWarning@@YAXPEAG@Z; _LogMsgWarning(ushort *)
0x1800175f1  jmp     loc_180017685
0x1800175f6  mov     rcx, rdi; unsigned __int16 *
0x1800175f9  call    ?_LogMsgError@@YAXPEAG@Z; _LogMsgError(ushort *)
0x1800175fe  jmp     loc_180017685
0x180017603  mov     eax, cs:dword_180027080
0x180017609  mov     ecx, 2
0x18001760e  mov     [rdi+1FFCh], si
0x180017615  cmp     eax, ecx
0x180017617  jbe     short loc_180017685
0x180017619  mov     rax, [rbp+57h+Format]
0x18001761d  lea     rdx, [rbp+57h+var_80]
0x180017621  mov     [rbp+57h+var_40], rdx
0x180017625  lea     edx, [rcx+2]
0x180017628  mov     [rbp+57h+var_38], rdx
0x18001762c  mov     dword ptr [rbp+57h+var_80], 8007007Ah
0x180017633  test    rax, rax
0x180017636  jz      short loc_18001764E
0x180017638  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001763c  inc     rcx
0x18001763f  cmp     [rax+rcx*2], si
0x180017643  jnz     short loc_18001763C
0x180017645  lea     ecx, ds:2[rcx*2]
0x18001764c  jmp     short loc_180017655
0x18001764e  lea     rax, dword_18001D62C
0x180017655  mov     [rbp+57h+var_50], rax
0x180017659  xor     r9d, r9d
0x18001765c  lea     rax, [rbp+57h+var_70]
0x180017660  mov     [rbp+57h+var_48], ecx
0x180017663  mov     [rsp+28h], rax
0x180017668  lea     rcx, dword_180027080
0x18001766f  mov     dword ptr [rsp+0B0h+var_90], edx
0x180017673  xor     r8d, r8d
0x180017676  lea     rdx, byte_180020F0B
0x18001767d  mov     [rbp+57h+var_44], esi
0x180017680  call    _tlgWriteTransfer_EventWriteTransfer
0x180017685  mov     rcx, [rbp+57h+var_30]
0x180017689  xor     rcx, rsp; StackCookie
0x18001768c  call    __security_check_cookie
0x180017691  add     rsp, 98h
0x180017698  pop     rdi
0x180017699  pop     rsi
0x18001769a  pop     rbx
0x18001769b  pop     rbp
0x18001769c  retn
```
