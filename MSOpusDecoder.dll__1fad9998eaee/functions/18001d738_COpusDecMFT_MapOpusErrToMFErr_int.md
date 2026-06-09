# COpusDecMFT::MapOpusErrToMFErr(int)

- ea: `0x18001d738`
- end: `0x18001d84e`
- name: `?MapOpusErrToMFErr@COpusDecMFT@@AEAAJH@Z`
- size: `278`
- prototype: `__int64 __fastcall(COpusDecMFT *this, int, int, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18001ce80`
- `0x18001d860`
- `0x18001e808`

## callees

- `0x1800010c8`
- `0x1800011dc`
- `0x1800018f0`
- `0x18001d738`

## pseudocode

```c
__int64 __fastcall COpusDecMFT::MapOpusErrToMFErr(COpusDecMFT *this, int a2, int a3, int a4)
{
  unsigned int v6; // ebx
  unsigned int v8; // [rsp+30h] [rbp-58h] BYREF
  COpusDecMFT *v9; // [rsp+38h] [rbp-50h] BYREF
  _QWORD v10[6]; // [rsp+40h] [rbp-48h] BYREF

  if ( (unsigned int)dword_180035090 > 4 )
  {
    v10[4] = &v8;
    v10[5] = 8;
    tlgWriteTransfer_EventWriteTransfer(&dword_180035090, word_1800306F2, 0, 0, 3, v10, this, v9);
  }
  switch ( a2 )
  {
    case -7:
      v6 = -2147024882;
      break;
    case -6:
      goto LABEL_13;
    case -5:
      v6 = -2147467263;
      break;
    case -4:
      v6 = -1072875829;
      break;
    case -3:
LABEL_13:
      v6 = -1072875810;
      break;
    case -2:
      v6 = -1072875855;
      break;
    case -1:
      v6 = -2147024809;
      break;
    default:
      v6 = a2 != 0 ? 0xC00D36DE : 0;
      break;
  }
  if ( (unsigned int)dword_180035090 > 4 )
  {
    v8 = v6;
    v9 = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      dword_180035090,
      (unsigned int)&word_18003058E,
      a3,
      a4,
      (__int64)&v9,
      (__int64)&v8);
  }
  return v6;
}

```

## disassembly

```asm
0x18001d738  mov     r11, rsp
0x18001d73b  mov     [r11+8], rbx
0x18001d73f  push    rdi
0x18001d740  sub     rsp, 80h
0x18001d747  mov     rax, cs:__security_cookie
0x18001d74e  xor     rax, rsp
0x18001d751  mov     [rsp+88h+var_18], rax
0x18001d756  mov     eax, cs:dword_180035090
0x18001d75c  mov     ebx, edx
0x18001d75e  mov     rdi, rcx
0x18001d761  cmp     eax, 4
0x18001d764  jbe     short loc_18001D7A3
0x18001d766  lea     rax, [r11-58h]
0x18001d76a  mov     [r11-58h], rcx
0x18001d76e  mov     [r11-28h], rax
0x18001d772  lea     rdx, word_1800306F2
0x18001d779  lea     rax, [r11-48h]
0x18001d77d  mov     qword ptr [r11-20h], 8
0x18001d785  mov     [r11-60h], rax
0x18001d789  lea     rcx, dword_180035090
0x18001d790  xor     r9d, r9d
0x18001d793  mov     dword ptr [rsp+88h+var_68], 3
0x18001d79b  xor     r8d, r8d
0x18001d79e  call    _tlgWriteTransfer_EventWriteTransfer
0x18001d7a3  cmp     ebx, 0FFFFFFF9h
0x18001d7a6  jz      short loc_18001D7F5
0x18001d7a8  cmp     ebx, 0FFFFFFFAh
0x18001d7ab  jz      short loc_18001D7E0
0x18001d7ad  cmp     ebx, 0FFFFFFFBh
0x18001d7b0  jz      short loc_18001D7EE
0x18001d7b2  cmp     ebx, 0FFFFFFFCh
0x18001d7b5  jz      short loc_18001D7E7
0x18001d7b7  cmp     ebx, 0FFFFFFFDh
0x18001d7ba  jz      short loc_18001D7E0
0x18001d7bc  cmp     ebx, 0FFFFFFFEh
0x18001d7bf  jz      short loc_18001D7D9
0x18001d7c1  cmp     ebx, 0FFFFFFFFh
0x18001d7c4  jz      short loc_18001D7D2
0x18001d7c6  neg     ebx
0x18001d7c8  sbb     ebx, ebx
0x18001d7ca  and     ebx, 0C00D36DEh
0x18001d7d0  jmp     short loc_18001D7FA
0x18001d7d2  mov     ebx, 80070057h
0x18001d7d7  jmp     short loc_18001D7FA
0x18001d7d9  mov     ebx, 0C00D36B1h
0x18001d7de  jmp     short loc_18001D7FA
0x18001d7e0  mov     ebx, 0C00D36DEh
0x18001d7e5  jmp     short loc_18001D7FA
0x18001d7e7  mov     ebx, 0C00D36CBh
0x18001d7ec  jmp     short loc_18001D7FA
0x18001d7ee  mov     ebx, 80004001h
0x18001d7f3  jmp     short loc_18001D7FA
0x18001d7f5  mov     ebx, 8007000Eh
0x18001d7fa  mov     ecx, cs:dword_180035090
0x18001d800  cmp     ecx, 4
0x18001d803  jbe     short loc_18001D82E
0x18001d805  lea     rax, [rsp+88h+var_58]
0x18001d80a  mov     [rsp+88h+var_58], ebx
0x18001d80e  mov     [rsp+88h+var_60], rax
0x18001d813  lea     rdx, word_18003058E
0x18001d81a  lea     rax, [rsp+88h+var_50]
0x18001d81f  mov     [rsp+88h+var_50], rdi
0x18001d824  mov     [rsp+88h+var_68], rax
0x18001d829  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001d82e  mov     eax, ebx
0x18001d830  mov     rcx, [rsp+88h+var_18]
0x18001d835  xor     rcx, rsp; StackCookie
0x18001d838  call    __security_check_cookie
0x18001d83d  mov     rbx, [rsp+88h+arg_0]
0x18001d845  add     rsp, 80h
0x18001d84c  pop     rdi
0x18001d84d  retn
```
