# ZtWriteSettings(_DNS_ZT_SETTINGS *,void *,HKEY__ *)

- ea: `0x180005134`
- end: `0x1800052bd`
- name: `?ZtWriteSettings@@YAJPEAU_DNS_ZT_SETTINGS@@PEAXPEAUHKEY__@@@Z`
- size: `393`
- prototype: `__int64 __fastcall(struct _DNS_ZT_SETTINGS *, void *, HKEY)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800049b0`

## callees

- `0x180003f58`
- `0x180005134`
- `0x180007130`
- `0x180008a60`
- `0x180009554`
- `0x180009adc`
- `0x180015008`
- `0x180015478`

## pseudocode

```c
__int64 __fastcall ZtWriteSettings(struct _DNS_ZT_SETTINGS *a1, void *a2, HKEY a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // eax
  __int64 v8; // rdx

  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_qqq(1026, 25, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, a1, a2, a3);
  if ( !a1 || !a2 || !a3 )
  {
    v6 = 87;
    goto LABEL_28;
  }
  v6 = 0;
  if ( (*((_BYTE *)a1 + 8) & 2) != 0 )
  {
    v7 = ZtRegWriteTrustedServers(*((unsigned int *)a1 + 8), *((_QWORD *)a1 + 3), a2, a3);
    v6 = v7;
    if ( v7 )
    {
      if ( (xmmword_18001F260 & 4) == 0 )
        return v6;
      v8 = 26;
      goto LABEL_27;
    }
  }
  if ( (*((_BYTE *)a1 + 8) & 8) != 0 )
  {
    v7 = ZtRegWriteClientCerts(*((_QWORD *)a1 + 7), a2, a3);
    v6 = v7;
    if ( v7 )
    {
      if ( (xmmword_18001F260 & 4) == 0 )
        return v6;
      v8 = 27;
      goto LABEL_27;
    }
  }
  if ( (*((_BYTE *)a1 + 8) & 0x10) != 0 )
  {
    v7 = ZtRegWriteTrustedCa(*((_QWORD *)a1 + 8), a2, a3);
    v6 = v7;
    if ( v7 )
    {
      if ( (xmmword_18001F260 & 4) == 0 )
        return v6;
      v8 = 28;
      goto LABEL_27;
    }
  }
  if ( (*((_BYTE *)a1 + 8) & 4) != 0 )
  {
    v7 = ZtRegWriteRules(*((_DWORD *)a1 + 12), *((_QWORD *)a1 + 5), (int)a3, (int)a2, a3);
    v6 = v7;
    if ( v7 )
    {
      if ( (xmmword_18001F260 & 4) == 0 )
        return v6;
      v8 = 29;
      goto LABEL_27;
    }
  }
  if ( (*((_BYTE *)a1 + 8) & 1) != 0 )
  {
    v7 = ZtRegWriteConfig(a3);
    v6 = v7;
    if ( v7 )
    {
      if ( (xmmword_18001F260 & 4) == 0 )
        return v6;
      v8 = 30;
LABEL_27:
      WPP_SF_d(1026, v8, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, v7);
    }
  }
LABEL_28:
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 31, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180005134  push    rbx
0x180005136  push    rbp
0x180005137  push    rsi
0x180005138  push    rdi
0x180005139  push    r12
0x18000513b  push    r15
0x18000513d  sub     rsp, 38h
0x180005141  mov     rsi, r8
0x180005144  mov     rbp, rdx
0x180005147  mov     rdi, rcx
0x18000514a  test    byte ptr cs:xmmword_18001F260, 4
0x180005151  lea     r12, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids
0x180005158  mov     r15d, 402h
0x18000515e  jz      short loc_18000517D
0x180005160  mov     [rsp+68h+var_40], r8
0x180005165  mov     edx, 19h
0x18000516a  mov     r8, r12
0x18000516d  mov     [rsp+68h+var_48], rbp
0x180005172  mov     ecx, r15d
0x180005175  mov     r9, rdi
0x180005178  call    WPP_SF_qqq
0x18000517d  test    rdi, rdi
0x180005180  jnz     short loc_18000518C
0x180005182  mov     ebx, 57h ; 'W'
0x180005187  jmp     loc_180005292
0x18000518c  test    rbp, rbp
0x18000518f  jz      short loc_180005182
0x180005191  test    rsi, rsi
0x180005194  jz      short loc_180005182
0x180005196  xor     ebx, ebx
0x180005198  test    byte ptr [rdi+8], 2
0x18000519c  jz      short loc_1800051CD
0x18000519e  mov     rdx, [rdi+18h]
0x1800051a2  mov     r9, rsi
0x1800051a5  mov     ecx, [rdi+20h]
0x1800051a8  mov     r8, rbp
0x1800051ab  call    ZtRegWriteTrustedServers
0x1800051b0  mov     ebx, eax
0x1800051b2  test    eax, eax
0x1800051b4  jz      short loc_1800051CD
0x1800051b6  test    byte ptr cs:xmmword_18001F260, 4
0x1800051bd  jz      loc_1800052AE
0x1800051c3  mov     edx, 1Ah
0x1800051c8  jmp     loc_180005284
0x1800051cd  test    byte ptr [rdi+8], 8
0x1800051d1  jz      short loc_1800051FF
0x1800051d3  mov     rcx, [rdi+38h]
0x1800051d7  mov     r8, rsi
0x1800051da  mov     rdx, rbp
0x1800051dd  call    ZtRegWriteClientCerts
0x1800051e2  mov     ebx, eax
0x1800051e4  test    eax, eax
0x1800051e6  jz      short loc_1800051FF
0x1800051e8  test    byte ptr cs:xmmword_18001F260, 4
0x1800051ef  jz      loc_1800052AE
0x1800051f5  mov     edx, 1Bh
0x1800051fa  jmp     loc_180005284
0x1800051ff  test    byte ptr [rdi+8], 10h
0x180005203  jz      short loc_18000522E
0x180005205  mov     rcx, [rdi+40h]
0x180005209  mov     r8, rsi
0x18000520c  mov     rdx, rbp
0x18000520f  call    ZtRegWriteTrustedCa
0x180005214  mov     ebx, eax
0x180005216  test    eax, eax
0x180005218  jz      short loc_18000522E
0x18000521a  test    byte ptr cs:xmmword_18001F260, 4
0x180005221  jz      loc_1800052AE
0x180005227  mov     edx, 1Ch
0x18000522c  jmp     short loc_180005284
0x18000522e  test    byte ptr [rdi+8], 4
0x180005232  jz      short loc_18000525E
0x180005234  mov     rdx, [rdi+28h]; int
0x180005238  mov     r9, rbp; int
0x18000523b  mov     ecx, [rdi+30h]; int
0x18000523e  mov     [rsp+68h+var_48], rsi; HKEY
0x180005243  call    ZtRegWriteRules
0x180005248  mov     ebx, eax
0x18000524a  test    eax, eax
0x18000524c  jz      short loc_18000525E
0x18000524e  test    byte ptr cs:xmmword_18001F260, 4
0x180005255  jz      short loc_1800052AE
0x180005257  mov     edx, 1Dh
0x18000525c  jmp     short loc_180005284
0x18000525e  test    byte ptr [rdi+8], 1
0x180005262  jz      short loc_180005292
0x180005264  mov     rdx, [rdi+10h]
0x180005268  mov     rcx, rsi; hKey
0x18000526b  call    ZtRegWriteConfig
0x180005270  mov     ebx, eax
0x180005272  test    eax, eax
0x180005274  jz      short loc_180005292
0x180005276  test    byte ptr cs:xmmword_18001F260, 4
0x18000527d  jz      short loc_1800052AE
0x18000527f  mov     edx, 1Eh
0x180005284  mov     r9d, eax
0x180005287  mov     r8, r12
0x18000528a  mov     ecx, r15d
0x18000528d  call    WPP_SF_d
0x180005292  test    byte ptr cs:xmmword_18001F260, 4
0x180005299  jz      short loc_1800052AE
0x18000529b  mov     edx, 1Fh
0x1800052a0  mov     ecx, r15d
0x1800052a3  mov     r9d, ebx
0x1800052a6  mov     r8, r12
0x1800052a9  call    WPP_SF_d
0x1800052ae  mov     eax, ebx
0x1800052b0  add     rsp, 38h
0x1800052b4  pop     r15
0x1800052b6  pop     r12
0x1800052b8  pop     rdi
0x1800052b9  pop     rsi
0x1800052ba  pop     rbp
0x1800052bb  pop     rbx
0x1800052bc  retn
```
