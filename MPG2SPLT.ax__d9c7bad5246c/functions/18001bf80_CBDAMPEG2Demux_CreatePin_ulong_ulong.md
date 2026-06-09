# CBDAMPEG2Demux::CreatePin(ulong,ulong *)

- ea: `0x18001bf80`
- end: `0x18001c0a0`
- name: `?CreatePin@CBDAMPEG2Demux@@UEAAJKPEAK@Z`
- size: `288`
- prototype: `__int64 __fastcall(CBDAMPEG2Demux *__hidden this, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001460`
- `0x180001e98`
- `0x180001f04`
- `0x180013b58`
- `0x180013f9c`
- `0x18001bf80`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001c06d`
- `KERNEL32!LeaveCriticalSection` at `0x18001c06d`
- `KERNEL32!EnterCriticalSection` at `0x18001c03e`
- `KERNEL32!EnterCriticalSection` at `0x18001c03e`

## pseudocode

```c
__int64 __fastcall CBDAMPEG2Demux::CreatePin(CBDAMPEG2Demux *this, int a2, unsigned int *a3)
{
  unsigned int v6; // esi
  __int64 result; // rax
  struct _RTL_CRITICAL_SECTION *v8; // rsi
  CMPEG2Demultiplexer *v9; // rcx
  int InputPinLocked; // ebx
  struct _AMMediaType v11; // [rsp+20h] [rbp-C8h] BYREF
  struct _AMMediaType Buffer; // [rsp+80h] [rbp-68h] BYREF

  v11.majortype.Data1 = 0;
  memset_0(&v11.majortype.Data2, 0, 0x54u);
  if ( !a3 )
    return 2147942487LL;
  if ( !a2 )
  {
    v8 = *(struct _RTL_CRITICAL_SECTION **)(*((_QWORD *)this + 1) + 80LL);
    EnterCriticalSection(v8);
    v9 = (CMPEG2Demultiplexer *)*((_QWORD *)this + 1);
    if ( *((_QWORD *)v9 + 20) )
    {
      InputPinLocked = -2147467259;
    }
    else
    {
      InputPinLocked = CMPEG2Demultiplexer::CreateInputPinLocked_(v9);
      if ( InputPinLocked >= 0 )
        *a3 = 0;
    }
    LeaveCriticalSection(v8);
    return (unsigned int)InputPinLocked;
  }
  if ( a2 != 1 )
    return 2147942487LL;
  while ( 1 )
  {
    v6 = *((_DWORD *)this + 13);
    if ( !v6 )
      v6 = 1;
    *((_DWORD *)this + 13) = v6 + 1;
    swprintf_s((wchar_t *const)&Buffer, 0x20u, L"%03d", v6, *(_QWORD *)&v11.majortype.Data1);
    result = CMPEG2Demultiplexer::CreateOutputPin_(*((CMPEG2Demultiplexer **)this + 1), &Buffer, &v11, 0);
    if ( (int)result >= 0 )
      break;
    if ( (_DWORD)result != -2147220947 )
      return result;
  }
  *a3 = v6;
  return result;
}

```

## disassembly

```asm
0x18001bf80  mov     [rsp+arg_8], rbx
0x18001bf85  push    rsi
0x18001bf86  push    rdi
0x18001bf87  push    r14
0x18001bf89  sub     rsp, 0D0h
0x18001bf90  mov     rax, cs:__security_cookie
0x18001bf97  xor     rax, rsp
0x18001bf9a  mov     [rsp+0E8h+var_28], rax
0x18001bfa2  mov     esi, edx
0x18001bfa4  mov     [rsp+0E8h+var_C8.majortype.Data1], 0
0x18001bfac  xor     edx, edx; Val
0x18001bfae  mov     rdi, r8
0x18001bfb1  mov     rbx, rcx
0x18001bfb4  lea     rcx, [rsp+0E8h+var_C8.majortype.Data2]; void *
0x18001bfb9  lea     r8d, [rdx+54h]; Size
0x18001bfbd  call    memset_0
0x18001bfc2  test    rdi, rdi
0x18001bfc5  jz      loc_18001C077
0x18001bfcb  test    esi, esi
0x18001bfcd  jz      short loc_18001C033
0x18001bfcf  mov     r14d, 1
0x18001bfd5  cmp     esi, r14d
0x18001bfd8  jnz     loc_18001C077
0x18001bfde  mov     esi, [rbx+34h]
0x18001bfe1  lea     r8, a03d; "%03d"
0x18001bfe8  test    esi, esi
0x18001bfea  lea     rcx, [rsp+0E8h+Buffer]; Buffer
0x18001bff2  mov     edx, 20h ; ' '; BufferCount
0x18001bff7  cmovz   esi, r14d
0x18001bffb  mov     r9d, esi
0x18001bffe  lea     eax, [rsi+1]
0x18001c001  mov     [rbx+34h], eax
0x18001c004  call    swprintf_s
0x18001c009  mov     rcx, [rbx+8]; this
0x18001c00d  lea     r8, [rsp+0E8h+var_C8]; struct _AMMediaType *
0x18001c012  xor     r9d, r9d; struct DEMUX_PIN_RECORD **
0x18001c015  lea     rdx, [rsp+0E8h+Buffer]; unsigned __int16 *
0x18001c01d  call    ?CreateOutputPin_@CMPEG2Demultiplexer@@AEAAJPEBGPEAU_AMMediaType@@PEAPEAUDEMUX_PIN_RECORD@@@Z; CMPEG2Demultiplexer::CreateOutputPin_(ushort const *,_AMMediaType *,DEMUX_PIN_RECORD * *)
0x18001c022  test    eax, eax
0x18001c024  jns     short loc_18001C02F
0x18001c026  cmp     eax, 8004022Dh
0x18001c02b  jz      short loc_18001BFDE
0x18001c02d  jmp     short loc_18001C07C
0x18001c02f  mov     [rdi], esi
0x18001c031  jmp     short loc_18001C07C
0x18001c033  mov     rax, [rbx+8]
0x18001c037  mov     rsi, [rax+50h]
0x18001c03b  mov     rcx, rsi; lpCriticalSection
0x18001c03e  call    cs:__imp_EnterCriticalSection
0x18001c044  mov     rcx, [rbx+8]; this
0x18001c048  cmp     qword ptr [rcx+0A0h], 0
0x18001c050  jnz     short loc_18001C065
0x18001c052  call    ?CreateInputPinLocked_@CMPEG2Demultiplexer@@AEAAJXZ; CMPEG2Demultiplexer::CreateInputPinLocked_(void)
0x18001c057  mov     ebx, eax
0x18001c059  test    eax, eax
0x18001c05b  js      short loc_18001C06A
0x18001c05d  mov     dword ptr [rdi], 0
0x18001c063  jmp     short loc_18001C06A
0x18001c065  mov     ebx, 80004005h
0x18001c06a  mov     rcx, rsi; lpCriticalSection
0x18001c06d  call    cs:__imp_LeaveCriticalSection
0x18001c073  mov     eax, ebx
0x18001c075  jmp     short loc_18001C07C
0x18001c077  mov     eax, 80070057h
0x18001c07c  mov     rcx, [rsp+0E8h+var_28]
0x18001c084  xor     rcx, rsp; StackCookie
0x18001c087  call    __security_check_cookie
0x18001c08c  mov     rbx, [rsp+0E8h+arg_8]
0x18001c094  add     rsp, 0D0h
0x18001c09b  pop     r14
0x18001c09d  pop     rdi
0x18001c09e  pop     rsi
0x18001c09f  retn
```
