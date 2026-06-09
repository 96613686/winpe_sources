# BdeSvcApplyGroupPolicyVolume(ushort const *)

- ea: `0x18001c1ec`
- end: `0x18001c3ce`
- name: `?BdeSvcApplyGroupPolicyVolume@@YAXPEBG@Z`
- size: `482`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800065b8`
- `0x18001b8c0`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18001b890`
- `0x18001c1ec`
- `0x180034070`

## import_xrefs

- `FVEAPI!FveApplyNkpCertChanges` at `0x18001c310`
- `FVEAPI!FveApplyNkpCertChanges` at `0x18001c310`
- `FVEAPI!FveApplyGroupPolicy` at `0x18001c2d5`
- `FVEAPI!FveApplyGroupPolicy` at `0x18001c2d5`
- `FVEAPI!FveOpenVolumeW` at `0x18001c289`
- `FVEAPI!FveOpenVolumeW` at `0x18001c289`
- `FVEAPI!FveCloseVolume` at `0x18001c378`
- `FVEAPI!FveCloseVolume` at `0x18001c378`

## pseudocode

```c
void __fastcall BdeSvcApplyGroupPolicyVolume(const unsigned __int16 *a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // eax
  int v4; // ebx
  int v5; // eax
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // [rsp+20h] [rbp-18h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v8 = -1;
  if ( a1 )
  {
    v3 = FveOpenVolumeW(a1, 1, &v8);
    v4 = v3;
    if ( v3 )
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v3);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 < 0 )
        goto LABEL_25;
    }
    v5 = FveApplyGroupPolicy(v8);
    if ( v5 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        134,
        WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
        (unsigned int)v5);
    v6 = FveApplyNkpCertChanges(v8);
    v7 = v6;
    if ( v6 < 0 && v6 != -2144272344 && v6 != -2144272228 && v6 != (unsigned int)FromNtStatus(-1071579135) )
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_25:
        if ( v8 != -1 )
        {
          FveCloseVolume(v8);
          v2 = (PVOID *)WPP_GLOBAL_Control;
          v8 = -1;
        }
        goto LABEL_27;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v7);
    }
LABEL_24:
    v2 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  if ( v2 == &WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)v2 + 28) & 2) != 0 )
  {
    WPP_SF_(v2[2], 132, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
    goto LABEL_24;
  }
LABEL_27:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_(v2[2], 136, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
}

```

## disassembly

```asm
0x18001c1ec  mov     [rsp+arg_8], rbx
0x18001c1f1  mov     [rsp+arg_10], rsi
0x18001c1f6  push    rdi
0x18001c1f7  sub     rsp, 30h
0x18001c1fb  mov     rax, cs:__security_cookie
0x18001c202  xor     rax, rsp
0x18001c205  mov     [rsp+38h+var_10], rax
0x18001c20a  mov     rbx, rcx
0x18001c20d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c214  lea     rdi, WPP_GLOBAL_Control
0x18001c21b  lea     rsi, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18001c222  cmp     rcx, rdi
0x18001c225  jz      short loc_18001C245
0x18001c227  test    byte ptr [rcx+1Ch], 20h
0x18001c22b  jz      short loc_18001C245
0x18001c22d  mov     rcx, [rcx+10h]
0x18001c231  mov     edx, 83h
0x18001c236  mov     r8, rsi
0x18001c239  call    WPP_SF_
0x18001c23e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c245  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFFh
0x18001c24e  test    rbx, rbx
0x18001c251  jnz     short loc_18001C27C
0x18001c253  cmp     rcx, rdi
0x18001c256  jz      loc_18001C3B0
0x18001c25c  test    byte ptr [rcx+1Ch], 2
0x18001c260  jz      loc_18001C394
0x18001c266  mov     rcx, [rcx+10h]
0x18001c26a  mov     edx, 84h
0x18001c26f  mov     r8, rsi
0x18001c272  call    WPP_SF_
0x18001c277  jmp     loc_18001C364
0x18001c27c  lea     r8, [rsp+38h+var_18]
0x18001c281  mov     edx, 1
0x18001c286  mov     rcx, rbx
0x18001c289  call    cs:__imp_FveOpenVolumeW
0x18001c290  nop     dword ptr [rax+rax+00h]
0x18001c295  mov     ebx, eax
0x18001c297  test    eax, eax
0x18001c299  jz      short loc_18001C2D0
0x18001c29b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2a2  cmp     rcx, rdi
0x18001c2a5  jz      short loc_18001C2C8
0x18001c2a7  test    byte ptr [rcx+1Ch], 40h
0x18001c2ab  jz      short loc_18001C2C8
0x18001c2ad  mov     rcx, [rcx+10h]
0x18001c2b1  mov     edx, 85h
0x18001c2b6  mov     r9d, eax
0x18001c2b9  mov     r8, rsi
0x18001c2bc  call    WPP_SF_d
0x18001c2c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2c8  test    ebx, ebx
0x18001c2ca  js      loc_18001C36B
0x18001c2d0  mov     rcx, [rsp+38h+var_18]
0x18001c2d5  call    cs:__imp_FveApplyGroupPolicy
0x18001c2dc  nop     dword ptr [rax+rax+00h]
0x18001c2e1  test    eax, eax
0x18001c2e3  jns     short loc_18001C30B
0x18001c2e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2ec  cmp     rcx, rdi
0x18001c2ef  jz      short loc_18001C30B
0x18001c2f1  test    byte ptr [rcx+1Ch], 2
0x18001c2f5  jz      short loc_18001C30B
0x18001c2f7  mov     rcx, [rcx+10h]
0x18001c2fb  mov     edx, 86h
0x18001c300  mov     r9d, eax
0x18001c303  mov     r8, rsi
0x18001c306  call    WPP_SF_d
0x18001c30b  mov     rcx, [rsp+38h+var_18]
0x18001c310  call    cs:__imp_FveApplyNkpCertChanges
0x18001c317  nop     dword ptr [rax+rax+00h]
0x18001c31c  mov     ebx, eax
0x18001c31e  test    eax, eax
0x18001c320  jns     short loc_18001C364
0x18001c322  cmp     eax, 80310028h
0x18001c327  jz      short loc_18001C364
0x18001c329  cmp     eax, 8031009Ch
0x18001c32e  jz      short loc_18001C364
0x18001c330  mov     ecx, 0C0210001h; int
0x18001c335  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18001c33a  cmp     ebx, eax
0x18001c33c  jz      short loc_18001C364
0x18001c33e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c345  cmp     rcx, rdi
0x18001c348  jz      short loc_18001C36B
0x18001c34a  test    byte ptr [rcx+1Ch], 2
0x18001c34e  jz      short loc_18001C36B
0x18001c350  mov     rcx, [rcx+10h]
0x18001c354  mov     edx, 87h
0x18001c359  mov     r9d, ebx
0x18001c35c  mov     r8, rsi
0x18001c35f  call    WPP_SF_d
0x18001c364  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c36b  cmp     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFFh
0x18001c371  jz      short loc_18001C394
0x18001c373  mov     rcx, [rsp+38h+var_18]
0x18001c378  call    cs:__imp_FveCloseVolume
0x18001c37f  nop     dword ptr [rax+rax+00h]
0x18001c384  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c38b  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFFh
0x18001c394  cmp     rcx, rdi
0x18001c397  jz      short loc_18001C3B0
0x18001c399  test    byte ptr [rcx+1Ch], 20h
0x18001c39d  jz      short loc_18001C3B0
0x18001c39f  mov     rcx, [rcx+10h]
0x18001c3a3  mov     edx, 88h
0x18001c3a8  mov     r8, rsi
0x18001c3ab  call    WPP_SF_
0x18001c3b0  mov     rcx, [rsp+38h+var_10]
0x18001c3b5  xor     rcx, rsp; StackCookie
0x18001c3b8  call    __security_check_cookie
0x18001c3bd  mov     rbx, [rsp+38h+arg_8]
0x18001c3c2  mov     rsi, [rsp+38h+arg_10]
0x18001c3c7  add     rsp, 30h
0x18001c3cb  pop     rdi
0x18001c3cc  retn
```
