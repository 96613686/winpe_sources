# Sid::Sid(void)

- ea: `0x180062344`
- end: `0x1800623e9`
- name: `??0Sid@@QEAA@XZ`
- size: `165`
- prototype: `Sid *__fastcall(Sid *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800625fc`
- `0x180063138`

## callees

- `0x180006ed4`
- `0x18000ecc0`
- `0x180062344`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800623a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800623a1`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18006237e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18006237e`

## pseudocode

```c
Sid *__fastcall Sid::Sid(Sid *this)
{
  signed int LastError; // eax
  DWORD cbSid; // [rsp+30h] [rbp+8h] BYREF

  cbSid = 68;
  *(_OWORD *)((char *)this + 72) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 7;
  *((_WORD *)this + 36) = 0;
  if ( !CreateWellKnownSid(WinNullSid, 0, this, &cbSid) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        23,
        WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids,
        (unsigned int)LastError);
    }
    memset_0(this, 0, 0x44u);
  }
  return this;
}

```

## disassembly

```asm
0x180062344  push    rbx
0x180062346  sub     rsp, 20h
0x18006234a  xorps   xmm0, xmm0
0x18006234d  mov     [rsp+28h+cbSid], 44h ; 'D'
0x180062355  movups  xmmword ptr [rcx+48h], xmm0
0x180062359  mov     qword ptr [rcx+58h], 0
0x180062361  lea     r9, [rsp+28h+cbSid]; cbSid
0x180062366  mov     qword ptr [rcx+60h], 7
0x18006236e  xor     eax, eax
0x180062370  mov     [rcx+48h], ax
0x180062374  mov     rbx, rcx
0x180062377  mov     r8, rcx; pSid
0x18006237a  xor     edx, edx; DomainSid
0x18006237c  xor     ecx, ecx; WellKnownSidType
0x18006237e  call    cs:__imp_CreateWellKnownSid
0x180062384  test    eax, eax
0x180062386  jnz     short loc_1800623E0
0x180062388  mov     rax, cs:WPP_GLOBAL_Control
0x18006238f  lea     rcx, WPP_GLOBAL_Control
0x180062396  cmp     rax, rcx
0x180062399  jz      short loc_1800623D2
0x18006239b  test    byte ptr [rax+1Ch], 1
0x18006239f  jz      short loc_1800623D2
0x1800623a1  call    cs:__imp_GetLastError
0x1800623a7  test    eax, eax
0x1800623a9  jle     short loc_1800623B3
0x1800623ab  movzx   eax, ax
0x1800623ae  or      eax, 80070000h
0x1800623b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800623ba  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x1800623c1  mov     edx, 17h
0x1800623c6  mov     r9d, eax
0x1800623c9  mov     rcx, [rcx+10h]
0x1800623cd  call    WPP_SF_d
0x1800623d2  xor     edx, edx; Val
0x1800623d4  mov     rcx, rbx; void *
0x1800623d7  lea     r8d, [rdx+44h]; Size
0x1800623db  call    memset_0
0x1800623e0  mov     rax, rbx
0x1800623e3  add     rsp, 20h
0x1800623e7  pop     rbx
0x1800623e8  retn
```
