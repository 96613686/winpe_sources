# ChangeApplicationServices::ReportChangeApplicationFinished(void)

- ea: `0x180048b10`
- end: `0x180048bc6`
- name: `?ReportChangeApplicationFinished@ChangeApplicationServices@@UEAAJXZ`
- size: `182`
- prototype: `__int64 __fastcall(ChangeApplicationServices *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180048b10`

## string_xrefs

- `0x180048b45`: `ChangeApplicationServices::ReportChangeApplicationFinished`
- `0x180048b98`: `ChangeApplicationServices::ReportChangeApplicationFinished`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::ReportChangeApplicationFinished(ChangeApplicationServices *this)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::ReportChangeApplicationFinished");
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 54) )
  {
    v3 = 0;
    *((_DWORD *)this + 54) = 0;
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v3 = -2147217379;
  }
  if ( v2 != &WPP_GLOBAL_Control && *((char *)v2 + 28) < 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v2[2],
      47,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::ReportChangeApplicationFinished",
      v3);
  return v3;
}

```

## disassembly

```asm
0x180048b10  mov     [rsp+arg_0], rbx
0x180048b15  mov     [rsp+arg_8], rsi
0x180048b1a  push    rdi
0x180048b1b  sub     rsp, 30h
0x180048b1f  mov     rdi, rcx
0x180048b22  mov     rcx, cs:WPP_GLOBAL_Control
0x180048b29  lea     rsi, WPP_GLOBAL_Control
0x180048b30  cmp     rcx, rsi
0x180048b33  jz      short loc_180048B64
0x180048b35  test    byte ptr [rcx+1Ch], 80h
0x180048b39  jz      short loc_180048B64
0x180048b3b  cmp     byte ptr [rcx+19h], 5
0x180048b3f  jb      short loc_180048B64
0x180048b41  mov     rcx, [rcx+10h]
0x180048b45  lea     r9, aChangeapplicat_51; "ChangeApplicationServices::ReportChange"...
0x180048b4c  mov     edx, 2Eh ; '.'
0x180048b51  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180048b58  call    WPP_SF_s
0x180048b5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180048b64  cmp     dword ptr [rdi+0D8h], 0
0x180048b6b  jnz     short loc_180048B74
0x180048b6d  mov     ebx, 8004101Dh
0x180048b72  jmp     short loc_180048B83
0x180048b74  xor     ebx, ebx
0x180048b76  mov     [rdi+0D8h], ebx
0x180048b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048b83  cmp     rcx, rsi
0x180048b86  jz      short loc_180048BB4
0x180048b88  test    byte ptr [rcx+1Ch], 80h
0x180048b8c  jz      short loc_180048BB4
0x180048b8e  cmp     byte ptr [rcx+19h], 5
0x180048b92  jb      short loc_180048BB4
0x180048b94  mov     rcx, [rcx+10h]
0x180048b98  lea     r9, aChangeapplicat_51; "ChangeApplicationServices::ReportChange"...
0x180048b9f  mov     edx, 2Fh ; '/'
0x180048ba4  mov     [rsp+38h+var_18], ebx
0x180048ba8  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180048baf  call    WPP_SF_sD
0x180048bb4  mov     rsi, [rsp+38h+arg_8]
0x180048bb9  mov     eax, ebx
0x180048bbb  mov     rbx, [rsp+38h+arg_0]
0x180048bc0  add     rsp, 30h
0x180048bc4  pop     rdi
0x180048bc5  retn
```
