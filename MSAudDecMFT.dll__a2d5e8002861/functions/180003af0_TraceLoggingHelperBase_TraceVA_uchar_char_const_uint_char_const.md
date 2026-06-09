# TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)

- ea: `0x180003af0`
- end: `0x180003c9d`
- name: `?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ`
- size: `429`
- prototype: `void(TraceLoggingHelperBase *__hidden this, unsigned __int8, const char *, unsigned int, const char *Format, ...)`
- caller_count: `41`
- callee_count: `4`
- tags: ``

## callers

- `0x180001740`
- `0x1800019d0`
- `0x18000205c`
- `0x180002140`
- `0x180002250`
- `0x1800022c0`
- `0x18000231c`
- `0x180002550`
- `0x180003550`
- `0x180003664`
- `0x180003ca4`
- `0x180003d64`
- `0x180003e24`
- `0x180003ec8`
- `0x18000467c`
- `0x180004e04`
- `0x180004e54`
- `0x180004fe0`
- `0x18003004c`
- `0x180030114`
- `0x180030340`
- `0x180030404`
- `0x180030550`
- `0x1800305d4`
- `0x180030924`
- `0x180037fd0`
- `0x18003d268`
- `0x18003e600`
- `0x18003f8c0`
- `0x18003fbe0`
- `0x180041630`
- `0x180041e50`
- `0x180042270`
- `0x1800429f0`
- `0x180048570`
- `0x180048894`
- `0x18004a850`
- `0x18004be4c`
- `0x180056dd0`
- `0x180057c60`
- `0x180058eac`

## callees

- `0x180001008`
- `0x180003af0`
- `0x18004d320`
- `0x180055288`

## pseudocode

```c
void TraceLoggingHelperBase::TraceVA(
        TraceLoggingHelperBase *this,
        unsigned __int8 a2,
        const char *a3,
        int a4,
        char *Format,
        ...)
{
  int v6; // ebx
  unsigned int v9; // eax
  char *v10; // rdx
  unsigned int *v11; // rcx
  int v12; // r8d
  int v13; // r9d
  unsigned int v14; // eax
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  char *v18; // rdx
  char **v19; // rax
  char **v20; // [rsp+38h] [rbp-C8h]
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  char *v22; // [rsp+48h] [rbp-B8h] BYREF
  char *v23; // [rsp+50h] [rbp-B0h] BYREF
  const char *v24; // [rsp+58h] [rbp-A8h] BYREF
  char Buffer[1024]; // [rsp+60h] [rbp-A0h] BYREF
  va_list ArgList; // [rsp+4C8h] [rbp+3C8h] BYREF

  va_start(ArgList, Format);
  v6 = a2;
  if ( (unsigned int)a2 < **((_DWORD **)this + 4) )
  {
    v22 = 0;
    v9 = vsnprintf(Buffer, 0x3FFu, Format, ArgList);
    if ( v9 >= 0x400 )
    {
      v10 = Format;
    }
    else
    {
      v10 = Buffer;
      if ( v9 != 1023 )
        goto LABEL_7;
    }
    Buffer[1023] = 0;
LABEL_7:
    v11 = (unsigned int *)*((_QWORD *)this + 4);
    v12 = (_DWORD)this + 8;
    v13 = (_DWORD)this + 8;
    if ( *((_DWORD *)this + 6) != 1 )
      v12 = 0;
    if ( *((_DWORD *)this + 6) != 2 )
      v13 = 0;
    v14 = *v11;
    v15 = v6 - 1;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( v17 )
        {
          if ( v17 != 1 )
          {
            if ( v14 <= 5 )
              return;
            v23 = v10;
            v20 = &v23;
            v18 = &byte_1800DC5C7;
            v22 = (char *)this + 8;
            v19 = &v22;
            goto LABEL_26;
          }
          if ( v14 <= 4 )
            return;
          v22 = v10;
          v18 = byte_1800DC439;
        }
        else
        {
          if ( v14 <= 3 )
            return;
          v22 = v10;
          v18 = byte_1800DC631;
        }
      }
      else
      {
        if ( v14 <= 2 )
          return;
        v22 = v10;
        v18 = byte_1800DC593;
      }
    }
    else
    {
      if ( v14 <= 1 )
        return;
      v22 = v10;
      v18 = byte_1800DC5FD;
    }
    v23 = (char *)this + 8;
    v20 = &v22;
    v19 = &v23;
LABEL_26:
    v21 = a4;
    v24 = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)v11,
      (_DWORD)v18,
      v12,
      v13,
      (__int64)v19,
      (__int64)&v24,
      (__int64)&v21,
      (__int64)v20);
  }
}

```

## disassembly

```asm
0x180003af0  push    rbp
0x180003af2  push    rbx
0x180003af3  push    rsi
0x180003af4  push    rdi
0x180003af5  push    r14
0x180003af7  lea     rbp, [rsp-370h]
0x180003aff  sub     rsp, 470h
0x180003b06  mov     rax, cs:__security_cookie
0x180003b0d  xor     rax, rsp
0x180003b10  mov     [rbp+390h+var_30], rax
0x180003b17  mov     rax, [rcx+20h]
0x180003b1b  mov     edi, r9d
0x180003b1e  movzx   ebx, dl
0x180003b21  mov     rsi, r8
0x180003b24  mov     r14, rcx
0x180003b27  mov     r10d, [rax]
0x180003b2a  cmp     ebx, r10d
0x180003b2d  jnb     loc_180003C7F
0x180003b33  mov     r8, [rbp+390h+Format]; Format
0x180003b3a  lea     r9, [rbp+390h+ArgList]; ArgList
0x180003b41  mov     edx, 3FFh; BufferCount
0x180003b46  mov     [rsp+490h+var_448], 0
0x180003b4f  lea     rcx, [rsp+490h+Buffer]; Buffer
0x180003b54  call    _vsnprintf
0x180003b59  test    eax, eax
0x180003b5b  js      short loc_180003B6D
0x180003b5d  cmp     eax, 3FFh
0x180003b62  ja      short loc_180003B6D
0x180003b64  lea     rdx, [rsp+490h+Buffer]
0x180003b69  jnz     short loc_180003B7B
0x180003b6b  jmp     short loc_180003B74
0x180003b6d  mov     rdx, [rbp+390h+Format]
0x180003b74  mov     [rbp+390h+var_31], 0
0x180003b7b  mov     rcx, [r14+20h]
0x180003b7f  lea     r10, [r14+8]
0x180003b83  xor     eax, eax
0x180003b85  mov     r8, r10
0x180003b88  cmp     dword ptr [r14+18h], 1
0x180003b8d  mov     r9, r10
0x180003b90  cmovnz  r8, rax
0x180003b94  cmp     dword ptr [r14+18h], 2
0x180003b99  cmovnz  r9, rax
0x180003b9d  mov     eax, [rcx]
0x180003b9f  sub     ebx, 1
0x180003ba2  jz      loc_180003C33
0x180003ba8  sub     ebx, 1
0x180003bab  jz      short loc_180003C20
0x180003bad  sub     ebx, 1
0x180003bb0  jz      short loc_180003C0D
0x180003bb2  cmp     ebx, 1
0x180003bb5  jz      short loc_180003BF6
0x180003bb7  cmp     eax, 5
0x180003bba  jbe     loc_180003C7F
0x180003bc0  lea     rax, [rsp+490h+var_440]
0x180003bc5  mov     [rsp+490h+var_440], rdx
0x180003bca  mov     [rsp+490h+var_458], rax
0x180003bcf  lea     rdx, byte_1800DC5C7
0x180003bd6  lea     rax, [rsp+490h+var_450]
0x180003bdb  mov     [rsp+490h+var_448], r10
0x180003be0  mov     [rsp+490h+var_460], rax
0x180003be5  lea     rax, [rsp+490h+var_438]
0x180003bea  mov     [rsp+490h+var_468], rax
0x180003bef  lea     rax, [rsp+490h+var_448]
0x180003bf4  jmp     short loc_180003C6C
0x180003bf6  cmp     eax, 4
0x180003bf9  jbe     loc_180003C7F
0x180003bff  mov     [rsp+490h+var_448], rdx
0x180003c04  lea     rdx, byte_1800DC439
0x180003c0b  jmp     short loc_180003C44
0x180003c0d  cmp     eax, 3
0x180003c10  jbe     short loc_180003C7F
0x180003c12  mov     [rsp+490h+var_448], rdx
0x180003c17  lea     rdx, byte_1800DC631
0x180003c1e  jmp     short loc_180003C44
0x180003c20  cmp     eax, 2
0x180003c23  jbe     short loc_180003C7F
0x180003c25  mov     [rsp+490h+var_448], rdx
0x180003c2a  lea     rdx, byte_1800DC593
0x180003c31  jmp     short loc_180003C44
0x180003c33  cmp     eax, 1
0x180003c36  jbe     short loc_180003C7F
0x180003c38  mov     [rsp+490h+var_448], rdx
0x180003c3d  lea     rdx, byte_1800DC5FD
0x180003c44  lea     rax, [rsp+490h+var_448]
0x180003c49  mov     [rsp+490h+var_440], r10
0x180003c4e  mov     [rsp+490h+var_458], rax
0x180003c53  lea     rax, [rsp+490h+var_450]
0x180003c58  mov     [rsp+490h+var_460], rax
0x180003c5d  lea     rax, [rsp+490h+var_438]
0x180003c62  mov     [rsp+490h+var_468], rax
0x180003c67  lea     rax, [rsp+490h+var_440]
0x180003c6c  mov     [rsp+490h+var_470], rax
0x180003c71  mov     [rsp+490h+var_450], edi
0x180003c75  mov     [rsp+490h+var_438], rsi
0x180003c7a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180003c7f  mov     rcx, [rbp+390h+var_30]
0x180003c86  xor     rcx, rsp; StackCookie
0x180003c89  call    __security_check_cookie
0x180003c8e  add     rsp, 470h
0x180003c95  pop     r14
0x180003c97  pop     rdi
0x180003c98  pop     rsi
0x180003c99  pop     rbx
0x180003c9a  pop     rbp
0x180003c9b  retn
```
