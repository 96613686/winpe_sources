# ClockVector::GetUpdateCount(ulong *)

- ea: `0x180087380`
- end: `0x18008743a`
- name: `?GetUpdateCount@ClockVector@@UEAAJPEAK@Z`
- size: `186`
- prototype: `__int64 __fastcall(ClockVector *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180087380`

## string_xrefs

- `0x1800873b2`: `ClockVector::GetUpdateCount`
- `0x180087413`: `ClockVector::GetUpdateCount`

## pseudocode

```c
__int64 __fastcall ClockVector::GetUpdateCount(ClockVector *this, unsigned int *a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      WPP_362d7c742a68350205e0bfe72ed984ca_Traceguids,
      "ClockVector::GetUpdateCount");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    if ( (*((_BYTE *)this + 36) & 1) != 0 && (*((_BYTE *)this + 36) & 2) != 0 )
    {
      v5 = 0;
      *a2 = *((_DWORD *)this + 8);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      v5 = -2147217379;
    }
  }
  else
  {
    v5 = -2147467261;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      35,
      (unsigned int)WPP_362d7c742a68350205e0bfe72ed984ca_Traceguids,
      (unsigned int)"ClockVector::GetUpdateCount",
      v5);
  return v5;
}

```

## disassembly

```asm
0x180087380  push    rbx
0x180087382  push    rbp
0x180087383  push    rsi
0x180087384  push    rdi
0x180087385  sub     rsp, 38h
0x180087389  mov     rdi, rdx
0x18008738c  mov     rsi, rcx
0x18008738f  mov     rcx, cs:WPP_GLOBAL_Control
0x180087396  lea     rbp, WPP_GLOBAL_Control
0x18008739d  cmp     rcx, rbp
0x1800873a0  jz      short loc_1800873D1
0x1800873a2  test    byte ptr [rcx+1Ch], 40h
0x1800873a6  jz      short loc_1800873D1
0x1800873a8  cmp     byte ptr [rcx+19h], 5
0x1800873ac  jb      short loc_1800873D1
0x1800873ae  mov     rcx, [rcx+10h]
0x1800873b2  lea     r9, aClockvectorGet_0; "ClockVector::GetUpdateCount"
0x1800873b9  mov     edx, 22h ; '"'
0x1800873be  lea     r8, WPP_362d7c742a68350205e0bfe72ed984ca_Traceguids
0x1800873c5  call    WPP_SF_s
0x1800873ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800873d1  test    rdi, rdi
0x1800873d4  jnz     short loc_1800873DD
0x1800873d6  mov     ebx, 80004003h
0x1800873db  jmp     short loc_1800873FE
0x1800873dd  test    byte ptr [rsi+24h], 1
0x1800873e1  jz      short loc_1800873E9
0x1800873e3  test    byte ptr [rsi+24h], 2
0x1800873e7  jnz     short loc_1800873F0
0x1800873e9  mov     ebx, 8004101Dh
0x1800873ee  jmp     short loc_1800873FE
0x1800873f0  mov     eax, [rsi+20h]
0x1800873f3  xor     ebx, ebx
0x1800873f5  mov     [rdi], eax
0x1800873f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800873fe  cmp     rcx, rbp
0x180087401  jz      short loc_18008742F
0x180087403  test    byte ptr [rcx+1Ch], 40h
0x180087407  jz      short loc_18008742F
0x180087409  cmp     byte ptr [rcx+19h], 5
0x18008740d  jb      short loc_18008742F
0x18008740f  mov     rcx, [rcx+10h]
0x180087413  lea     r9, aClockvectorGet_0; "ClockVector::GetUpdateCount"
0x18008741a  mov     edx, 23h ; '#'
0x18008741f  mov     [rsp+58h+var_38], ebx
0x180087423  lea     r8, WPP_362d7c742a68350205e0bfe72ed984ca_Traceguids
0x18008742a  call    WPP_SF_sD
0x18008742f  mov     eax, ebx
0x180087431  add     rsp, 38h
0x180087435  pop     rdi
0x180087436  pop     rsi
0x180087437  pop     rbp
0x180087438  pop     rbx
0x180087439  retn
```
