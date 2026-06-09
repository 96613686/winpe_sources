# CommonUtil::UtilRegGetValue(HKEY__ *,wchar_t const *,ulong *,unsigned __int64 *,void *)

- ea: `0x140004dc0`
- end: `0x140004f34`
- name: `?UtilRegGetValue@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAKPEA_KPEAX@Z`
- size: `372`
- prototype: `int(CommonUtil *__hidden this, HKEY, const wchar_t *, unsigned int *, unsigned __int64 *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140004f34`

## callees

- `0x140004dc0`
- `0x140005050`
- `0x140005c20`
- `0x14001dac4`
- `0x140020220`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140004e1a`
- `ADVAPI32!RegQueryValueExW` at `0x140004e1a`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegGetValue(
        CommonUtil *this,
        const WCHAR *a2,
        DWORD *a3,
        unsigned int *a4,
        BYTE *lpData)
{
  __int64 v5; // r15
  int v9; // ebx
  LSTATUS v10; // eax
  signed int v11; // esi
  __int64 v12; // rax
  DWORD cbData; // [rsp+30h] [rbp-48h] BYREF

  v5 = *(_QWORD *)a4;
  cbData = *(_QWORD *)a4;
  if ( cbData != v5 )
  {
    v9 = -2147024809;
    goto LABEL_10;
  }
  v10 = RegQueryValueExW((HKEY)this, a2, 0, a3, lpData, &cbData);
  v11 = (unsigned __int16)v10 | 0x80070000;
  if ( v10 <= 0 )
    v11 = v10;
  if ( v11 >= 0 )
  {
    if ( lpData && (v12 = cbData, (unsigned __int64)cbData > *(_QWORD *)a4) )
    {
      v9 = -2147024662;
    }
    else
    {
      v12 = cbData;
      v9 = 0;
    }
    goto LABEL_9;
  }
  v9 = -2147024894;
  if ( v11 == -2147024894 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_4145d653138e3b1ee6f2a9af82386a7e_Traceguids, a2);
  }
  else
  {
    v9 = -2147024662;
    if ( v11 == -2147024662 )
    {
      v12 = cbData;
      if ( *(_QWORD *)a4 < (unsigned __int64)cbData )
      {
LABEL_9:
        *(_QWORD *)a4 = v12;
        goto LABEL_10;
      }
      v9 = -2147418113;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          (unsigned int)WPP_4145d653138e3b1ee6f2a9af82386a7e_Traceguids,
          (_DWORD)a2,
          v11);
      v9 = v11;
    }
  }
LABEL_10:
  if ( v9 >= 0 )
    return CommonUtil::UtilRegPostGetValue(a2, v5, *a3, a4, lpData);
  else
    return (unsigned int)v9;
}

```

## disassembly

```asm
0x140004dc0  push    rbx
0x140004dc2  push    rbp
0x140004dc3  push    rsi
0x140004dc4  push    rdi
0x140004dc5  push    r12
0x140004dc7  push    r14
0x140004dc9  push    r15
0x140004dcb  sub     rsp, 40h
0x140004dcf  mov     rax, cs:__security_cookie
0x140004dd6  xor     rax, rsp
0x140004dd9  mov     [rsp+78h+var_40], rax
0x140004dde  mov     r15, [r9]
0x140004de1  mov     rdi, r9
0x140004de4  mov     r14, [rsp+78h+arg_20]
0x140004dec  mov     r12, r8
0x140004def  mov     eax, r15d
0x140004df2  mov     rbp, rdx
0x140004df5  mov     [rsp+78h+cbData], eax
0x140004df9  cmp     rax, r15
0x140004dfc  jz      short loc_140004E05
0x140004dfe  mov     ebx, 80070057h
0x140004e03  jmp     short loc_140004E4D
0x140004e05  lea     rax, [rsp+78h+cbData]
0x140004e0a  mov     r9, r12; lpType
0x140004e0d  mov     [rsp+78h+lpcbData], rax; lpcbData
0x140004e12  xor     r8d, r8d; lpReserved
0x140004e15  mov     [rsp+78h+lpData], r14; lpData
0x140004e1a  call    cs:__imp_RegQueryValueExW
0x140004e20  movzx   esi, ax
0x140004e23  or      esi, 80070000h
0x140004e29  test    eax, eax
0x140004e2b  cmovle  esi, eax
0x140004e2e  mov     eax, esi
0x140004e30  shr     eax, 1Fh
0x140004e33  test    al, al
0x140004e35  jnz     short loc_140004E69
0x140004e37  test    r14, r14
0x140004e3a  jz      short loc_140004E61
0x140004e3c  mov     eax, [rsp+78h+cbData]
0x140004e40  cmp     rax, [rdi]
0x140004e43  jbe     short loc_140004E61
0x140004e45  mov     ebx, 800700EAh
0x140004e4a  mov     [rdi], rax
0x140004e4d  mov     ecx, ebx
0x140004e4f  shr     ecx, 1Fh
0x140004e52  test    cl, cl
0x140004e54  jz      loc_140004F01
0x140004e5a  mov     eax, ebx
0x140004e5c  jmp     loc_140004F18
0x140004e61  mov     eax, [rsp+78h+cbData]
0x140004e65  xor     ebx, ebx
0x140004e67  jmp     short loc_140004E4A
0x140004e69  mov     ebx, 80070002h
0x140004e6e  cmp     esi, ebx
0x140004e70  jnz     short loc_140004EA5
0x140004e72  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e79  lea     rax, WPP_GLOBAL_Control
0x140004e80  cmp     rcx, rax
0x140004e83  jz      short loc_140004E4D
0x140004e85  test    byte ptr [rcx+1Ch], 4
0x140004e89  jz      short loc_140004E4D
0x140004e8b  mov     rcx, [rcx+10h]
0x140004e8f  lea     r8, WPP_4145d653138e3b1ee6f2a9af82386a7e_Traceguids
0x140004e96  mov     edx, 14h
0x140004e9b  mov     r9, rbp
0x140004e9e  call    WPP_SF_S
0x140004ea3  jmp     short loc_140004E4D
0x140004ea5  mov     ebx, 800700EAh
0x140004eaa  cmp     esi, ebx
0x140004eac  jz      short loc_140004EEA
0x140004eae  mov     rcx, cs:WPP_GLOBAL_Control
0x140004eb5  lea     rax, WPP_GLOBAL_Control
0x140004ebc  cmp     rcx, rax
0x140004ebf  jz      short loc_140004EE3
0x140004ec1  test    byte ptr [rcx+1Ch], 1
0x140004ec5  jz      short loc_140004EE3
0x140004ec7  mov     rcx, [rcx+10h]
0x140004ecb  lea     r8, WPP_4145d653138e3b1ee6f2a9af82386a7e_Traceguids
0x140004ed2  mov     edx, 15h
0x140004ed7  mov     dword ptr [rsp+78h+lpData], esi
0x140004edb  mov     r9, rbp
0x140004ede  call    WPP_SF_Sd
0x140004ee3  mov     ebx, esi
0x140004ee5  jmp     loc_140004E4D
0x140004eea  mov     eax, [rsp+78h+cbData]
0x140004eee  cmp     [rdi], rax
0x140004ef1  jb      loc_140004E4A
0x140004ef7  mov     ebx, 8000FFFFh
0x140004efc  jmp     loc_140004E4D
0x140004f01  mov     r8d, [r12]
0x140004f05  mov     r9, rdi
0x140004f08  mov     rdx, r15
0x140004f0b  mov     [rsp+78h+lpData], r14
0x140004f10  mov     rcx, rbp
0x140004f13  call    CommonUtil__UtilRegPostGetValue
0x140004f18  mov     rcx, [rsp+78h+var_40]
0x140004f1d  xor     rcx, rsp; StackCookie
0x140004f20  call    __security_check_cookie
0x140004f25  add     rsp, 40h
0x140004f29  pop     r15
0x140004f2b  pop     r14
0x140004f2d  pop     r12
0x140004f2f  pop     rdi
0x140004f30  pop     rsi
0x140004f31  pop     rbp
0x140004f32  pop     rbx
0x140004f33  retn
```
