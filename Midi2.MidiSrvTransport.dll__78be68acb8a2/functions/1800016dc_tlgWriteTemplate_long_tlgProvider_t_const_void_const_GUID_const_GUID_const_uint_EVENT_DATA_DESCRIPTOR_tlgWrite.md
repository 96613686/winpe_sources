# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800016dc`
- end: `0x1800017c7`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `235`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18000aa80`
- `0x180012448`
- `0x1800126e4`
- `0x180012830`
- `0x180012964`
- `0x1800136c0`
- `0x180013d98`

## callees

- `0x18000163c`
- `0x1800016dc`
- `0x180002470`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 **a7)
{
  __int64 v9; // rcx
  __int64 *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  const unsigned __int16 *v13; // rdx
  int v14; // ecx
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+30h] [rbp-68h] BYREF
  const unsigned __int16 *v17; // [rsp+50h] [rbp-48h]
  int v18; // [rsp+58h] [rbp-40h]
  int v19; // [rsp+5Ch] [rbp-3Ch]
  __int64 v20; // [rsp+60h] [rbp-38h]
  __int64 v21; // [rsp+68h] [rbp-30h]
  __int64 *v22; // [rsp+70h] [rbp-28h]
  int v23; // [rsp+78h] [rbp-20h]
  int v24; // [rsp+7Ch] [rbp-1Ch]

  v9 = -1;
  v10 = *a7;
  if ( *a7 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)v10 + v11) );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = qword_180017FF0;
    v12 = 2;
  }
  v23 = v12;
  v20 = a6;
  v22 = v10;
  v24 = 0;
  v21 = 8;
  v13 = *a5;
  if ( *a5 )
  {
    do
      ++v9;
    while ( *((_BYTE *)v13 + v9) );
    v14 = v9 + 1;
  }
  else
  {
    v13 = &word_18001783A;
    v14 = 1;
  }
  v17 = v13;
  v18 = v14;
  v19 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 5u, &v16);
}

```

## disassembly

```asm
0x1800016dc  sub     rsp, 98h
0x1800016e3  mov     rax, cs:__security_cookie
0x1800016ea  xor     rax, rsp
0x1800016ed  mov     [rsp+98h+var_18], rax
0x1800016f5  mov     rax, [rsp+98h+arg_30]
0x1800016fd  mov     r11, rdx
0x180001700  mov     r10, rcx
0x180001703  xor     r8d, r8d
0x180001706  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000170a  mov     rdx, [rax]
0x18000170d  test    rdx, rdx
0x180001710  jz      short loc_180001728
0x180001712  mov     rax, rcx
0x180001715  inc     rax
0x180001718  cmp     [rdx+rax*2], r8w
0x18000171d  jnz     short loc_180001715
0x18000171f  lea     eax, ds:2[rax*2]
0x180001726  jmp     short loc_180001734
0x180001728  lea     rdx, qword_180017FF0
0x18000172f  mov     eax, 2
0x180001734  mov     [rsp+98h+var_20], eax
0x180001738  mov     rax, [rsp+98h+arg_28]
0x180001740  mov     [rsp+98h+var_38], rax
0x180001745  mov     rax, [rsp+98h+arg_20]
0x18000174d  mov     [rsp+98h+var_28], rdx
0x180001752  mov     [rsp+98h+var_1C], r8d
0x180001757  mov     [rsp+98h+var_30], 8
0x180001760  mov     rdx, [rax]
0x180001763  test    rdx, rdx
0x180001766  jz      short loc_180001775
0x180001768  inc     rcx
0x18000176b  cmp     [rdx+rcx], r8b
0x18000176f  jnz     short loc_180001768
0x180001771  inc     ecx
0x180001773  jmp     short loc_180001781
0x180001775  lea     rdx, word_18001783A
0x18000177c  mov     ecx, 1
0x180001781  lea     rax, [rsp+98h+var_68]
0x180001786  mov     [rsp+98h+var_48], rdx
0x18000178b  mov     [rsp+98h+var_40], ecx
0x18000178f  xor     r9d, r9d
0x180001792  mov     [rsp+98h+var_70], rax
0x180001797  mov     rdx, r11
0x18000179a  mov     rcx, r10
0x18000179d  mov     [rsp+98h+var_78], 5
0x1800017a5  mov     [rsp+98h+var_3C], r8d
0x1800017aa  call    _tlgWriteTransfer_EventWriteTransfer
0x1800017af  mov     rcx, [rsp+98h+var_18]
0x1800017b7  xor     rcx, rsp; StackCookie
0x1800017ba  call    __security_check_cookie
0x1800017bf  add     rsp, 98h
0x1800017c6  retn
```
