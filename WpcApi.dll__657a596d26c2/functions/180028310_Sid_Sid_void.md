# Sid::Sid(void)

- ea: `0x180028310`
- end: `0x1800283b5`
- name: `??0Sid@@QEAA@XZ`
- size: `165`
- prototype: `Sid *__fastcall(Sid *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800284b8`
- `0x180028aa4`

## callees

- `0x180003d14`
- `0x18000b29c`
- `0x180028310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002836d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002836d`
- `ADVAPI32!CreateWellKnownSid` at `0x18002834a`
- `ADVAPI32!CreateWellKnownSid` at `0x18002834a`

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
0x180028310  push    rbx
0x180028312  sub     rsp, 20h
0x180028316  xorps   xmm0, xmm0
0x180028319  mov     [rsp+28h+cbSid], 44h ; 'D'
0x180028321  movups  xmmword ptr [rcx+48h], xmm0
0x180028325  mov     qword ptr [rcx+58h], 0
0x18002832d  lea     r9, [rsp+28h+cbSid]; cbSid
0x180028332  mov     qword ptr [rcx+60h], 7
0x18002833a  xor     eax, eax
0x18002833c  mov     [rcx+48h], ax
0x180028340  mov     rbx, rcx
0x180028343  mov     r8, rcx; pSid
0x180028346  xor     edx, edx; DomainSid
0x180028348  xor     ecx, ecx; WellKnownSidType
0x18002834a  call    cs:__imp_CreateWellKnownSid
0x180028350  test    eax, eax
0x180028352  jnz     short loc_1800283AC
0x180028354  mov     rax, cs:WPP_GLOBAL_Control
0x18002835b  lea     rcx, WPP_GLOBAL_Control
0x180028362  cmp     rax, rcx
0x180028365  jz      short loc_18002839E
0x180028367  test    byte ptr [rax+1Ch], 1
0x18002836b  jz      short loc_18002839E
0x18002836d  call    cs:__imp_GetLastError
0x180028373  test    eax, eax
0x180028375  jle     short loc_18002837F
0x180028377  movzx   eax, ax
0x18002837a  or      eax, 80070000h
0x18002837f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028386  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x18002838d  mov     edx, 17h
0x180028392  mov     r9d, eax
0x180028395  mov     rcx, [rcx+10h]
0x180028399  call    WPP_SF_d
0x18002839e  xor     edx, edx; Val
0x1800283a0  mov     rcx, rbx; void *
0x1800283a3  lea     r8d, [rdx+44h]; Size
0x1800283a7  call    memset_0
0x1800283ac  mov     rax, rbx
0x1800283af  add     rsp, 20h
0x1800283b3  pop     rbx
0x1800283b4  retn
```
