# _tip_OmadmClientAadTokenExpirationTipTest::evaluate(void)

- ea: `0x180078a24`
- end: `0x180078c1b`
- name: `?evaluate@_tip_OmadmClientAadTokenExpirationTipTest@@QEAAXXZ`
- size: `503`
- prototype: `void __fastcall(_tip_OmadmClientAadTokenExpirationTipTest *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800789a0`

## callees

- `0x180078a24`
- `0x180079308`

## string_xrefs

- `0x180078a8b`: `reason::device_token_expiration_not_detected`
- `0x180078a42`: `reason::user_token_expiration_not_detected`
- `0x180078b0e`: `reason::device_token_expiration_detected_but_fixed`
- `0x180078ad4`: `reason::user_token_expiration_detected_but_fixed`
- `0x180078b7e`: `reason::device_token_expiration_detected_but_not_fixed`
- `0x180078b47`: `reason::user_token_expiration_detected_but_not_fixed`

## pseudocode

```c
void __fastcall _tip_OmadmClientAadTokenExpirationTipTest::evaluate(
        _tip_OmadmClientAadTokenExpirationTipTest *this,
        const char *a2)
{
  int v3; // ecx
  _BYTE *v4; // rax
  const char *v5; // rax
  __int16 v6; // r10
  __int64 v7; // r9
  __int64 v8; // rdx
  const char *v9; // rax
  char v10; // r8
  __int64 v11; // r9
  __int64 v12; // rcx
  char v13; // r10
  __int16 v14; // r8
  __int64 v15; // r9
  char v16; // r10
  __int64 v17; // r9
  char v18; // r10
  __int64 v19; // r9
  char v20; // r10
  __int64 v21; // r9
  char v22; // r10
  __int64 v23; // rax

  v3 = *((_DWORD *)this + 5);
  v4 = (char *)this + 16;
  if ( !v3 )
  {
    if ( !*v4 )
    {
      v5 = tip2::details::reason_string((tip2::details *)"reason::user_token_expiration_not_detected", a2);
      v8 = *(_QWORD *)(v7 + 8);
      if ( *(_BYTE *)(v8 + 152) != (_BYTE)v6 )
        return;
      *(_BYTE *)(v8 + 152) = 1;
      *(_WORD *)(v8 + 154) = v6;
      goto LABEL_5;
    }
    if ( *v4 == 1 )
    {
      v9 = tip2::details::reason_string((tip2::details *)"reason::device_token_expiration_not_detected", a2);
      v12 = *(_QWORD *)(v11 + 8);
      if ( *(_BYTE *)(v12 + 152) != v13 )
        return;
      *(_BYTE *)(v12 + 152) = v10;
      *(_WORD *)(v12 + 154) = 4;
      goto LABEL_9;
    }
    goto LABEL_24;
  }
  if ( v3 == 1 )
  {
    if ( !*v4 )
    {
      v5 = tip2::details::reason_string((tip2::details *)"reason::user_token_expiration_detected_but_fixed", a2);
      v8 = *(_QWORD *)(v15 + 8);
      if ( *(_BYTE *)(v8 + 152) != v16 )
        return;
      *(_BYTE *)(v8 + 152) = 2;
      *(_WORD *)(v8 + 154) = v14;
      goto LABEL_5;
    }
    if ( *v4 == 1 )
    {
      v5 = tip2::details::reason_string((tip2::details *)"reason::device_token_expiration_detected_but_fixed", a2);
      v8 = *(_QWORD *)(v17 + 8);
      if ( *(_BYTE *)(v8 + 152) != v18 )
        return;
      *(_BYTE *)(v8 + 152) = 2;
      *(_WORD *)(v8 + 154) = 5;
      goto LABEL_5;
    }
  }
  else if ( v3 > 1 )
  {
    if ( !*v4 )
    {
      v5 = tip2::details::reason_string((tip2::details *)"reason::user_token_expiration_detected_but_not_fixed", a2);
      v8 = *(_QWORD *)(v19 + 8);
      if ( *(_BYTE *)(v8 + 152) != v20 )
        return;
      *(_BYTE *)(v8 + 152) = 3;
      *(_WORD *)(v8 + 154) = 2;
LABEL_5:
      *(_QWORD *)(v8 + 160) = v5;
      return;
    }
    if ( *v4 == 1 )
    {
      v9 = tip2::details::reason_string((tip2::details *)"reason::device_token_expiration_detected_but_not_fixed", a2);
      v12 = *(_QWORD *)(v21 + 8);
      if ( *(_BYTE *)(v12 + 152) == v22 )
      {
        *(_BYTE *)(v12 + 152) = 3;
        *(_WORD *)(v12 + 154) = 6;
LABEL_9:
        *(_QWORD *)(v12 + 160) = v9;
        return;
      }
      return;
    }
  }
LABEL_24:
  v23 = *((_QWORD *)this + 1);
  if ( *(_QWORD *)(v23 + 80) )
  {
    if ( *(_BYTE *)(v23 + 152) )
      return;
    *(_BYTE *)(v23 + 152) = 3;
    *(_WORD *)(v23 + 154) = 0x4000;
  }
  else if ( (*(_DWORD *)(v23 + 56) & 0x200) != 0 )
  {
    if ( *(_BYTE *)(v23 + 152) )
      return;
    *(_BYTE *)(v23 + 152) = 1;
    *(_WORD *)(v23 + 154) = 0x8000;
  }
  else
  {
    if ( *(_BYTE *)(v23 + 152) )
      return;
    *(_BYTE *)(v23 + 152) = 3;
    *(_WORD *)(v23 + 154) = 16385;
  }
  *(_QWORD *)(v23 + 160) = 0;
}

```

## disassembly

```asm
0x180078a24  sub     rsp, 28h
0x180078a28  mov     r9, rcx
0x180078a2b  xor     r10d, r10d
0x180078a2e  mov     ecx, [rcx+14h]
0x180078a31  lea     rax, [r9+10h]
0x180078a35  test    ecx, ecx
0x180078a37  jnz     loc_180078AC4
0x180078a3d  cmp     [rax], r10b
0x180078a40  jnz     short loc_180078A7A
0x180078a42  lea     rcx, aReasonUserToke; "reason::user_token_expiration_not_detec"...
0x180078a49  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180078a4e  mov     rdx, [r9+8]; char *
0x180078a52  cmp     [rdx+98h], r10b
0x180078a59  jnz     loc_180078C15
0x180078a5f  mov     byte ptr [rdx+98h], 1
0x180078a66  mov     [rdx+9Ah], r10w
0x180078a6e  mov     [rdx+0A0h], rax
0x180078a75  jmp     loc_180078C15
0x180078a7a  test    ecx, ecx
0x180078a7c  jnz     short loc_180078AC4
0x180078a7e  lea     r8d, [rcx+1]
0x180078a82  cmp     [rax], r8b
0x180078a85  jnz     loc_180078BAC
0x180078a8b  lea     rcx, aReasonDeviceTo_1; "reason::device_token_expiration_not_det"...
0x180078a92  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180078a97  mov     rcx, [r9+8]
0x180078a9b  cmp     [rcx+98h], r10b
0x180078aa2  jnz     loc_180078C15
0x180078aa8  mov     [rcx+98h], r8b
0x180078aaf  mov     word ptr [rcx+9Ah], 4
0x180078ab8  mov     [rcx+0A0h], rax
0x180078abf  jmp     loc_180078C15
0x180078ac4  mov     r8d, 1
0x180078aca  cmp     ecx, r8d
0x180078acd  jnz     short loc_180078B40
0x180078acf  cmp     [rax], r10b
0x180078ad2  jnz     short loc_180078B05
0x180078ad4  lea     rcx, aReasonUserToke_1; "reason::user_token_expiration_detected_"...
0x180078adb  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180078ae0  mov     rdx, [r9+8]; char *
0x180078ae4  cmp     [rdx+98h], r10b
0x180078aeb  jnz     loc_180078C15
0x180078af1  mov     byte ptr [rdx+98h], 2
0x180078af8  mov     [rdx+9Ah], r8w
0x180078b00  jmp     loc_180078A6E
0x180078b05  cmp     [rax], r8b
0x180078b08  jnz     loc_180078BAC
0x180078b0e  lea     rcx, aReasonDeviceTo_0; "reason::device_token_expiration_detecte"...
0x180078b15  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180078b1a  mov     rdx, [r9+8]; char *
0x180078b1e  cmp     [rdx+98h], r10b
0x180078b25  jnz     loc_180078C15
0x180078b2b  mov     byte ptr [rdx+98h], 2
0x180078b32  mov     word ptr [rdx+9Ah], 5
0x180078b3b  jmp     loc_180078A6E
0x180078b40  jle     short loc_180078BAC
0x180078b42  cmp     [rax], r10b
0x180078b45  jnz     short loc_180078B79
0x180078b47  lea     rcx, aReasonUserToke_0; "reason::user_token_expiration_detected_"...
0x180078b4e  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180078b53  mov     rdx, [r9+8]; char *
0x180078b57  cmp     [rdx+98h], r10b
0x180078b5e  jnz     loc_180078C15
0x180078b64  mov     byte ptr [rdx+98h], 3
0x180078b6b  mov     word ptr [rdx+9Ah], 2
0x180078b74  jmp     loc_180078A6E
0x180078b79  cmp     [rax], r8b
0x180078b7c  jnz     short loc_180078BAC
0x180078b7e  lea     rcx, aReasonDeviceTo; "reason::device_token_expiration_detecte"...
0x180078b85  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180078b8a  mov     rcx, [r9+8]
0x180078b8e  cmp     [rcx+98h], r10b
0x180078b95  jnz     short loc_180078C15
0x180078b97  mov     byte ptr [rcx+98h], 3
0x180078b9e  mov     word ptr [rcx+9Ah], 6
0x180078ba7  jmp     loc_180078AB8
0x180078bac  mov     rax, [r9+8]
0x180078bb0  cmp     [rax+50h], r10
0x180078bb4  jz      short loc_180078BD1
0x180078bb6  cmp     [rax+98h], r10b
0x180078bbd  jnz     short loc_180078C15
0x180078bbf  mov     byte ptr [rax+98h], 3
0x180078bc6  mov     word ptr [rax+9Ah], 4000h
0x180078bcf  jmp     short loc_180078C0E
0x180078bd1  test    dword ptr [rax+38h], 200h
0x180078bd8  jnz     short loc_180078BF5
0x180078bda  cmp     [rax+98h], r10b
0x180078be1  jnz     short loc_180078C15
0x180078be3  mov     byte ptr [rax+98h], 3
0x180078bea  mov     word ptr [rax+9Ah], 4001h
0x180078bf3  jmp     short loc_180078C0E
0x180078bf5  cmp     [rax+98h], r10b
0x180078bfc  jnz     short loc_180078C15
0x180078bfe  mov     [rax+98h], r8b
0x180078c05  mov     word ptr [rax+9Ah], 8000h
0x180078c0e  mov     [rax+0A0h], r10
0x180078c15  add     rsp, 28h
0x180078c19  retn
```
