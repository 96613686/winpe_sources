# DeleteCredentialsFromCredMan

- ea: `0x180050b74`
- end: `0x180050cdf`
- name: `DeleteCredentialsFromCredMan`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180052a20`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18004033c`
- `0x180050b74`

## import_xrefs

- `api-ms-win-security-credentials-l1-1-0!CredDeleteA` at `0x180050c51`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteA` at `0x180050c65`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteA` at `0x180050c51`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteA` at `0x180050c65`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180050c2e`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180050c42`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180050c2e`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180050c42`

## pseudocode

```c
__int64 __fastcall DeleteCredentialsFromCredMan(__int64 a1)
{
  struct _LIST_ENTRY *v2; // rcx
  unsigned int v3; // edi
  __int64 UserData; // rax

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 138, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = 0;
  if ( (*(_DWORD *)(a1 + 112) & 0x20) != 0 )
  {
    UserData = GetUserData(a1 + 32, 6);
    if ( UserData && *(_DWORD *)(UserData + 20) >= 0xC28u )
    {
      if ( (*(_BYTE *)(UserData + 24) & 8) != 0 )
      {
        CredDeleteW(L"*Session", 3u, 0);
        CredDeleteW(L"*Session", 2u, 0);
      }
      else
      {
        CredDeleteA("*Session", 3u, 0);
        CredDeleteA("*Session", 2u, 0);
      }
      *(_DWORD *)(a1 + 112) &= ~0x20u;
    }
    else
    {
      v3 = 1168;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v3;
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_21;
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 140, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, 1168);
    }
    goto LABEL_20;
  }
  if ( v2 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v3;
  if ( (HIDWORD(v2[1].Blink) & 0x2000) != 0 && BYTE1(v2[1].Blink) >= 5u )
  {
    WPP_SF_(v2[1].Flink, 139, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
LABEL_20:
    v2 = WPP_GLOBAL_Control;
  }
LABEL_21:
  if ( v2 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v2[1].Blink) & 0x2000) != 0
    && BYTE1(v2[1].Blink) >= 6u )
  {
    WPP_SF_d(v2[1].Flink, 141, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180050b74  push    rbx
0x180050b76  push    rbp
0x180050b77  push    rsi
0x180050b78  push    rdi
0x180050b79  sub     rsp, 28h
0x180050b7d  mov     rbx, rcx
0x180050b80  mov     rcx, cs:WPP_GLOBAL_Control
0x180050b87  lea     rbp, WPP_GLOBAL_Control
0x180050b8e  mov     esi, 2000h
0x180050b93  cmp     rcx, rbp
0x180050b96  jz      short loc_180050BBF
0x180050b98  test    [rcx+1Ch], esi
0x180050b9b  jz      short loc_180050BBF
0x180050b9d  cmp     byte ptr [rcx+19h], 6
0x180050ba1  jb      short loc_180050BBF
0x180050ba3  mov     rcx, [rcx+10h]
0x180050ba7  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180050bae  mov     edx, 8Ah
0x180050bb3  call    WPP_SF_
0x180050bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180050bbf  mov     eax, [rbx+70h]
0x180050bc2  xor     edi, edi
0x180050bc4  test    al, 20h
0x180050bc6  jnz     short loc_180050BFE
0x180050bc8  cmp     rcx, rbp
0x180050bcb  jz      loc_180050CD4
0x180050bd1  test    [rcx+1Ch], esi
0x180050bd4  jz      loc_180050CAC
0x180050bda  cmp     byte ptr [rcx+19h], 5
0x180050bde  jb      loc_180050CAC
0x180050be4  mov     rcx, [rcx+10h]
0x180050be8  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180050bef  mov     edx, 8Bh
0x180050bf4  call    WPP_SF_
0x180050bf9  jmp     loc_180050CA5
0x180050bfe  lea     rcx, [rbx+20h]
0x180050c02  mov     edx, 6
0x180050c07  call    GetUserData
0x180050c0c  test    rax, rax
0x180050c0f  jz      short loc_180050C71
0x180050c11  cmp     dword ptr [rax+14h], 0C28h
0x180050c18  jb      short loc_180050C71
0x180050c1a  xor     r8d, r8d; Flags
0x180050c1d  test    byte ptr [rax+18h], 8
0x180050c21  lea     edx, [r8+3]; Type
0x180050c25  jz      short loc_180050C4A
0x180050c27  lea     rcx, TargetName; "*Session"
0x180050c2e  call    cs:__imp_CredDeleteW
0x180050c34  xor     r8d, r8d; Flags
0x180050c37  lea     rcx, TargetName; "*Session"
0x180050c3e  lea     edx, [r8+2]; Type
0x180050c42  call    cs:__imp_CredDeleteW
0x180050c48  jmp     short loc_180050C6B
0x180050c4a  lea     rcx, aSession_0; "*Session"
0x180050c51  call    cs:__imp_CredDeleteA
0x180050c57  xor     r8d, r8d; Flags
0x180050c5a  lea     rcx, aSession_0; "*Session"
0x180050c61  lea     edx, [r8+2]; Type
0x180050c65  call    cs:__imp_CredDeleteA
0x180050c6b  and     dword ptr [rbx+70h], 0FFFFFFDFh
0x180050c6f  jmp     short loc_180050CA5
0x180050c71  mov     edi, 490h
0x180050c76  mov     rcx, cs:WPP_GLOBAL_Control
0x180050c7d  cmp     rcx, rbp
0x180050c80  jz      short loc_180050CD4
0x180050c82  test    [rcx+1Ch], esi
0x180050c85  jz      short loc_180050CAC
0x180050c87  cmp     byte ptr [rcx+19h], 2
0x180050c8b  jb      short loc_180050CAC
0x180050c8d  mov     rcx, [rcx+10h]
0x180050c91  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180050c98  mov     edx, 8Ch
0x180050c9d  mov     r9d, edi
0x180050ca0  call    WPP_SF_d
0x180050ca5  mov     rcx, cs:WPP_GLOBAL_Control
0x180050cac  cmp     rcx, rbp
0x180050caf  jz      short loc_180050CD4
0x180050cb1  test    [rcx+1Ch], esi
0x180050cb4  jz      short loc_180050CD4
0x180050cb6  cmp     byte ptr [rcx+19h], 6
0x180050cba  jb      short loc_180050CD4
0x180050cbc  mov     rcx, [rcx+10h]
0x180050cc0  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180050cc7  mov     edx, 8Dh
0x180050ccc  mov     r9d, edi
0x180050ccf  call    WPP_SF_d
0x180050cd4  mov     eax, edi
0x180050cd6  add     rsp, 28h
0x180050cda  pop     rdi
0x180050cdb  pop     rsi
0x180050cdc  pop     rbp
0x180050cdd  pop     rbx
0x180050cde  retn
```
