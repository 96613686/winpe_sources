# CFbrProcessor::AddSidToObjectsSecurityDescriptor(void *,_SE_OBJECT_TYPE,void *,ulong)

- ea: `0x180078800`
- end: `0x180078cc8`
- name: `?AddSidToObjectsSecurityDescriptor@CFbrProcessor@@IEAAJPEAXW4_SE_OBJECT_TYPE@@0K@Z`
- size: `1224`
- prototype: `__int64 __fastcall(CFbrProcessor *this, void *, enum _SE_OBJECT_TYPE, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180078cd0`

## callees

- `0x180078800`
- `0x180079724`
- `0x180079770`
- `0x18007a404`
- `0x18019b31c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b8f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800789c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180078a4f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800789c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180078a4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078c41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078c99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078ca7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078c41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078c99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078ca7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800788bd`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800788bd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800789a8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800789a8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180078ace`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180078ace`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180078b61`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180078b61`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180078bcc`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180078bcc`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180078921`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180078921`

## pseudocode

```c
__int64 __fastcall CFbrProcessor::AddSidToObjectsSecurityDescriptor(
        CFbrProcessor *this,
        void *a2,
        enum _SE_OBJECT_TYPE a3,
        void *a4,
        unsigned int a5)
{
  void *v5; // r14
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v9; // rdx
  signed int SecurityInfo; // ebx
  unsigned int v11; // esi
  unsigned int v12; // eax
  DWORD LengthSid; // r15d
  WORD v14; // r12
  struct _ACL *v15; // rax
  struct _ACL *v16; // rbp
  unsigned int v17; // eax
  char *v18; // rax
  unsigned int v19; // eax
  signed int v20; // eax
  unsigned int v21; // ebx
  unsigned int v22; // eax
  __int64 v23; // rdx
  signed int v24; // eax
  int v25; // ebx
  signed int LastError; // eax
  signed int v27; // esi
  unsigned int v28; // ebx
  unsigned int v29; // eax
  unsigned int v30; // eax
  PACL ppDacl; // [rsp+70h] [rbp+8h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+78h] [rbp+10h] BYREF

  v5 = 0;
  ppDacl = 0;
  hMem = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 57;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids,
      CurrentThreadActivityIdPrefix,
      -2147024809);
LABEL_7:
    SecurityInfo = -2147024809;
    goto LABEL_75;
  }
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 58;
    goto LABEL_6;
  }
  if ( !IsValidSid(a4) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 59;
    goto LABEL_6;
  }
  SecurityInfo = GetSecurityInfo(a2, SE_KERNEL_OBJECT, 4u, 0, 0, &ppDacl, 0, &hMem);
  if ( SecurityInfo )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( SecurityInfo > 0 )
        v11 = (unsigned __int16)SecurityInfo | 0x80070000;
      else
        v11 = SecurityInfo;
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids, v12, v11);
    }
    if ( SecurityInfo > 0 )
      SecurityInfo = (unsigned __int16)SecurityInfo | 0x80070000;
    goto LABEL_75;
  }
  SecurityInfo = 0;
  if ( ppDacl )
  {
    LengthSid = GetLengthSid(a4);
    v14 = ppDacl->AclSize + LengthSid + 8;
    v15 = (struct _ACL *)LocalAlloc(0x40u, v14);
    v16 = v15;
    if ( !v15 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids,
          v17,
          -2147024882);
      }
      SecurityInfo = -2147024882;
      goto LABEL_75;
    }
    memcpy_0(v15, ppDacl, ppDacl->AclSize);
    v16->AclSize = v14;
    v18 = (char *)LocalAlloc(0x40u, (unsigned __int16)(LengthSid + 8));
    v5 = v18;
    if ( !v18 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids,
          v19,
          -2147024882);
      }
      SecurityInfo = -2147024882;
      goto LABEL_70;
    }
    *(_WORD *)v18 = 0;
    *((_WORD *)v18 + 1) = LengthSid + 8;
    *((_DWORD *)v18 + 1) = a5;
    if ( CopySid(LengthSid, v18 + 8, a4) )
    {
      if ( AddAce(v16, 2u, 0xFFFFFFFF, v5, (unsigned __int16)(LengthSid + 8)) )
      {
        v27 = SetSecurityInfo(a2, SE_KERNEL_OBJECT, 4u, 0, 0, v16, 0);
        if ( v27 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( v27 > 0 )
              v28 = (unsigned __int16)v27 | 0x80070000;
            else
              v28 = v27;
            v29 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              65,
              WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids,
              v29,
              v28);
          }
          if ( v27 > 0 )
          {
            v25 = (unsigned __int16)v27;
            goto LABEL_69;
          }
          SecurityInfo = v27;
        }
LABEL_70:
        LocalFree(v16);
        goto LABEL_75;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v21 = LastError;
        if ( LastError > 0 )
          v21 = (unsigned __int16)LastError | 0x80070000;
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        v23 = 64;
        goto LABEL_48;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = GetLastError();
      v21 = v20;
      if ( v20 > 0 )
        v21 = (unsigned __int16)v20 | 0x80070000;
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      v23 = 63;
LABEL_48:
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids, v22, v21);
    }
    v24 = GetLastError();
    SecurityInfo = v24;
    if ( v24 > 0 )
    {
      v25 = (unsigned __int16)v24;
LABEL_69:
      SecurityInfo = v25 | 0x80070000;
      goto LABEL_70;
    }
    goto LABEL_70;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v30 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids, v30);
  }
LABEL_75:
  if ( hMem )
    LocalFree(hMem);
  if ( v5 )
    LocalFree(v5);
  return (unsigned int)SecurityInfo;
}

```

## disassembly

```asm
0x180078800  mov     rax, rsp
0x180078803  mov     [rax+18h], rbx
0x180078807  mov     [rax+20h], rbp
0x18007880b  mov     [rax+8], rcx
0x18007880f  push    rsi
0x180078810  push    rdi
0x180078811  push    r12
0x180078813  push    r14
0x180078815  push    r15
0x180078817  sub     rsp, 40h
0x18007881b  xor     r14d, r14d
0x18007881e  mov     qword ptr [rax+8], 0
0x180078826  mov     qword ptr [rax+10h], 0
0x18007882e  mov     rdi, r9
0x180078831  mov     rsi, rdx
0x180078834  test    rdx, rdx
0x180078837  jnz     short loc_18007888C
0x180078839  mov     rcx, cs:WPP_GLOBAL_Control
0x180078840  lea     rax, WPP_GLOBAL_Control
0x180078847  cmp     rcx, rax
0x18007884a  jz      short loc_180078882
0x18007884c  test    byte ptr [rcx+1Ch], 8
0x180078850  jz      short loc_180078882
0x180078852  cmp     byte ptr [rcx+19h], 2
0x180078856  jb      short loc_180078882
0x180078858  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007885d  lea     edx, [rsi+39h]
0x180078860  mov     rcx, cs:WPP_GLOBAL_Control
0x180078867  lea     r8, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids
0x18007886e  mov     r9d, eax
0x180078871  mov     dword ptr [rsp+68h+ppsidGroup], 80070057h
0x180078879  mov     rcx, [rcx+10h]
0x18007887d  call    WPP_SF_Dd
0x180078882  mov     ebx, 80070057h
0x180078887  jmp     loc_180078C8F
0x18007888c  test    rdi, rdi
0x18007888f  jnz     short loc_1800788BA
0x180078891  mov     rcx, cs:WPP_GLOBAL_Control
0x180078898  lea     rax, WPP_GLOBAL_Control
0x18007889f  cmp     rcx, rax
0x1800788a2  jz      short loc_180078882
0x1800788a4  test    byte ptr [rcx+1Ch], 8
0x1800788a8  jz      short loc_180078882
0x1800788aa  cmp     byte ptr [rcx+19h], 2
0x1800788ae  jb      short loc_180078882
0x1800788b0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800788b5  lea     edx, [rdi+3Ah]
0x1800788b8  jmp     short loc_180078860
0x1800788ba  mov     rcx, rdi; pSid
0x1800788bd  call    cs:__imp_IsValidSid
0x1800788c3  test    eax, eax
0x1800788c5  jnz     short loc_1800788F5
0x1800788c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800788ce  lea     rax, WPP_GLOBAL_Control
0x1800788d5  cmp     rcx, rax
0x1800788d8  jz      short loc_180078882
0x1800788da  test    byte ptr [rcx+1Ch], 8
0x1800788de  jz      short loc_180078882
0x1800788e0  cmp     byte ptr [rcx+19h], 2
0x1800788e4  jb      short loc_180078882
0x1800788e6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800788eb  mov     edx, 3Bh ; ';'
0x1800788f0  jmp     loc_180078860
0x1800788f5  xor     r9d, r9d; ppsidOwner
0x1800788f8  lea     rax, [rsp+68h+hMem]
0x1800788fd  mov     [rsp+68h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180078902  mov     rcx, rsi; handle
0x180078905  lea     rax, [rsp+68h+arg_0]
0x18007890a  mov     [rsp+68h+ppSacl], r14; ppSacl
0x18007890f  mov     [rsp+68h+ppDacl], rax; ppDacl
0x180078914  lea     edx, [r9+6]; ObjectType
0x180078918  mov     [rsp+68h+ppsidGroup], r14; ppsidGroup
0x18007891d  lea     r8d, [r9+4]; SecurityInfo
0x180078921  call    cs:__imp_GetSecurityInfo
0x180078927  mov     ebx, eax
0x180078929  test    eax, eax
0x18007892b  jz      short loc_180078998
0x18007892d  mov     rcx, cs:WPP_GLOBAL_Control
0x180078934  lea     rax, WPP_GLOBAL_Control
0x18007893b  mov     edi, 80070000h
0x180078940  cmp     rcx, rax
0x180078943  jz      short loc_180078986
0x180078945  test    byte ptr [rcx+1Ch], 8
0x180078949  jz      short loc_180078986
0x18007894b  cmp     byte ptr [rcx+19h], 2
0x18007894f  jb      short loc_180078986
0x180078951  test    ebx, ebx
0x180078953  jg      short loc_180078959
0x180078955  mov     esi, ebx
0x180078957  jmp     short loc_18007895E
0x180078959  movzx   esi, bx
0x18007895c  or      esi, edi
0x18007895e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078963  mov     rcx, cs:WPP_GLOBAL_Control
0x18007896a  lea     r8, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids
0x180078971  mov     edx, 3Ch ; '<'
0x180078976  mov     dword ptr [rsp+68h+ppsidGroup], esi
0x18007897a  mov     r9d, eax
0x18007897d  mov     rcx, [rcx+10h]
0x180078981  call    WPP_SF_Dd
0x180078986  test    ebx, ebx
0x180078988  jle     loc_180078C8F
0x18007898e  movzx   ebx, bx
0x180078991  or      ebx, edi
0x180078993  jmp     loc_180078C8F
0x180078998  xor     ebx, ebx
0x18007899a  cmp     [rsp+68h+arg_0], rbx
0x18007899f  jz      loc_180078C49
0x1800789a5  mov     rcx, rdi; pSid
0x1800789a8  call    cs:__imp_GetLengthSid
0x1800789ae  mov     rcx, [rsp+68h+arg_0]
0x1800789b3  mov     r15d, eax
0x1800789b6  lea     edx, [rax+8]
0x1800789b9  add     dx, [rcx+2]
0x1800789bd  lea     ecx, [rbx+40h]; uFlags
0x1800789c0  movzx   r12d, dx
0x1800789c4  mov     edx, r12d; uBytes
0x1800789c7  call    cs:__imp_LocalAlloc
0x1800789cd  mov     rbp, rax
0x1800789d0  test    rax, rax
0x1800789d3  jnz     short loc_180078A28
0x1800789d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800789dc  lea     rax, WPP_GLOBAL_Control
0x1800789e3  cmp     rcx, rax
0x1800789e6  jz      short loc_180078A1E
0x1800789e8  test    byte ptr [rcx+1Ch], 8
0x1800789ec  jz      short loc_180078A1E
0x1800789ee  cmp     byte ptr [rcx+19h], 2
0x1800789f2  jb      short loc_180078A1E
0x1800789f4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800789f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180078a00  lea     edx, [rbx+3Dh]
0x180078a03  mov     r9d, eax
0x180078a06  mov     dword ptr [rsp+68h+ppsidGroup], 8007000Eh
0x180078a0e  lea     r8, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids
0x180078a15  mov     rcx, [rcx+10h]
0x180078a19  call    WPP_SF_Dd
0x180078a1e  mov     ebx, 8007000Eh
0x180078a23  jmp     loc_180078C8F
0x180078a28  mov     rdx, [rsp+68h+arg_0]; Src
0x180078a2d  mov     rcx, rbp; void *
0x180078a30  movzx   r8d, word ptr [rdx+2]; Size
0x180078a35  call    memcpy_0
0x180078a3a  lea     eax, [r15+8]
0x180078a3e  mov     [rbp+2], r12w
0x180078a43  movzx   r12d, ax
0x180078a47  mov     ecx, 40h ; '@'; uFlags
0x180078a4c  mov     edx, r12d; uBytes
0x180078a4f  call    cs:__imp_LocalAlloc
0x180078a55  mov     r14, rax
0x180078a58  test    rax, rax
0x180078a5b  jnz     short loc_180078AB1
0x180078a5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180078a64  lea     rax, WPP_GLOBAL_Control
0x180078a6b  cmp     rcx, rax
0x180078a6e  jz      short loc_180078AA7
0x180078a70  test    byte ptr [rcx+1Ch], 8
0x180078a74  jz      short loc_180078AA7
0x180078a76  cmp     byte ptr [rcx+19h], 2
0x180078a7a  jb      short loc_180078AA7
0x180078a7c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078a81  mov     rcx, cs:WPP_GLOBAL_Control
0x180078a88  lea     edx, [r14+3Eh]
0x180078a8c  mov     r9d, eax
0x180078a8f  mov     dword ptr [rsp+68h+ppsidGroup], 8007000Eh
0x180078a97  lea     r8, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids
0x180078a9e  mov     rcx, [rcx+10h]
0x180078aa2  call    WPP_SF_Dd
0x180078aa7  mov     ebx, 8007000Eh
0x180078aac  jmp     loc_180078C3E
0x180078ab1  mov     [rax], bx
0x180078ab4  lea     rdx, [r14+8]; pDestinationSid
0x180078ab8  mov     [rax+2], r12w
0x180078abd  mov     r8, rdi; pSourceSid
0x180078ac0  mov     eax, [rsp+68h+arg_20]
0x180078ac7  mov     ecx, r15d; nDestinationSidLength
0x180078aca  mov     [r14+4], eax
0x180078ace  call    cs:__imp_CopySid
0x180078ad4  test    eax, eax
0x180078ad6  jnz     short loc_180078B4D
0x180078ad8  mov     rcx, cs:WPP_GLOBAL_Control
0x180078adf  lea     rax, WPP_GLOBAL_Control
0x180078ae6  mov     edi, 80070000h
0x180078aeb  cmp     rcx, rax
0x180078aee  jz      short loc_180078B35
0x180078af0  test    byte ptr [rcx+1Ch], 8
0x180078af4  jz      short loc_180078B35
0x180078af6  cmp     byte ptr [rcx+19h], 2
0x180078afa  jb      short loc_180078B35
0x180078afc  call    cs:__imp_GetLastError
0x180078b02  mov     ebx, eax
0x180078b04  test    eax, eax
0x180078b06  jle     short loc_180078B0D
0x180078b08  movzx   ebx, ax
0x180078b0b  or      ebx, edi
0x180078b0d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078b12  mov     edx, 3Fh ; '?'
0x180078b17  mov     rcx, cs:WPP_GLOBAL_Control
0x180078b1e  lea     r8, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids
0x180078b25  mov     r9d, eax
0x180078b28  mov     dword ptr [rsp+68h+ppsidGroup], ebx
0x180078b2c  mov     rcx, [rcx+10h]
0x180078b30  call    WPP_SF_Dd
0x180078b35  call    cs:__imp_GetLastError
0x180078b3b  mov     ebx, eax
0x180078b3d  test    eax, eax
0x180078b3f  jle     loc_180078C3E
0x180078b45  movzx   ebx, ax
0x180078b48  jmp     loc_180078C3C
0x180078b4d  mov     r9, r14; pAceList
0x180078b50  mov     dword ptr [rsp+68h+ppsidGroup], r12d; nAceListLength
0x180078b55  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x180078b59  mov     edx, 2; dwAceRevision
0x180078b5e  mov     rcx, rbp; pAcl
0x180078b61  call    cs:__imp_AddAce
0x180078b67  test    eax, eax
0x180078b69  jnz     short loc_180078BAF
0x180078b6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180078b72  lea     rax, WPP_GLOBAL_Control
0x180078b79  mov     edi, 80070000h
0x180078b7e  cmp     rcx, rax
0x180078b81  jz      short loc_180078B35
0x180078b83  test    byte ptr [rcx+1Ch], 8
0x180078b87  jz      short loc_180078B35
0x180078b89  cmp     byte ptr [rcx+19h], 2
0x180078b8d  jb      short loc_180078B35
0x180078b8f  call    cs:__imp_GetLastError
0x180078b95  mov     ebx, eax
0x180078b97  test    eax, eax
0x180078b99  jle     short loc_180078BA0
0x180078b9b  movzx   ebx, ax
0x180078b9e  or      ebx, edi
0x180078ba0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078ba5  mov     edx, 40h ; '@'
0x180078baa  jmp     loc_180078B17
0x180078baf  xor     r9d, r9d; psidOwner
0x180078bb2  mov     [rsp+68h+ppSacl], rbx; pSacl
0x180078bb7  mov     [rsp+68h+ppDacl], rbp; pDacl
0x180078bbc  mov     rcx, rsi; handle
0x180078bbf  mov     [rsp+68h+ppsidGroup], rbx; psidGroup
0x180078bc4  lea     edx, [r9+6]; ObjectType
0x180078bc8  lea     r8d, [r9+4]; SecurityInfo
0x180078bcc  call    cs:__imp_SetSecurityInfo
0x180078bd2  mov     esi, eax
0x180078bd4  test    eax, eax
0x180078bd6  jz      short loc_180078C3E
0x180078bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180078bdf  lea     rax, WPP_GLOBAL_Control
0x180078be6  mov     edi, 80070000h
0x180078beb  cmp     rcx, rax
0x180078bee  jz      short loc_180078C31
0x180078bf0  test    byte ptr [rcx+1Ch], 8
0x180078bf4  jz      short loc_180078C31
0x180078bf6  cmp     byte ptr [rcx+19h], 2
0x180078bfa  jb      short loc_180078C31
0x180078bfc  test    esi, esi
0x180078bfe  jg      short loc_180078C04
0x180078c00  mov     ebx, esi
0x180078c02  jmp     short loc_180078C09
0x180078c04  movzx   ebx, si
0x180078c07  or      ebx, edi
0x180078c09  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180078c15  lea     r8, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids
0x180078c1c  mov     edx, 41h ; 'A'
0x180078c21  mov     dword ptr [rsp+68h+ppsidGroup], ebx
0x180078c25  mov     r9d, eax
0x180078c28  mov     rcx, [rcx+10h]
0x180078c2c  call    WPP_SF_Dd
0x180078c31  test    esi, esi
0x180078c33  jg      short loc_180078C39
0x180078c35  mov     ebx, esi
0x180078c37  jmp     short loc_180078C3E
0x180078c39  movzx   ebx, si
0x180078c3c  or      ebx, edi
0x180078c3e  mov     rcx, rbp; hMem
0x180078c41  call    cs:__imp_LocalFree
0x180078c47  jmp     short loc_180078C8F
0x180078c49  mov     rcx, cs:WPP_GLOBAL_Control
0x180078c50  lea     rax, WPP_GLOBAL_Control
0x180078c57  cmp     rcx, rax
0x180078c5a  jz      short loc_180078C8F
0x180078c5c  test    dword ptr [rcx+1Ch], 100h
0x180078c63  jz      short loc_180078C8F
0x180078c65  cmp     byte ptr [rcx+19h], 2
0x180078c69  jb      short loc_180078C8F
0x180078c6b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078c70  mov     rcx, cs:WPP_GLOBAL_Control
0x180078c77  lea     r8, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids
0x180078c7e  mov     edx, 42h ; 'B'
0x180078c83  mov     r9d, eax
0x180078c86  mov     rcx, [rcx+10h]
0x180078c8a  call    WPP_SF_d
0x180078c8f  mov     rcx, [rsp+68h+hMem]; hMem
0x180078c94  test    rcx, rcx
0x180078c97  jz      short loc_180078C9F
0x180078c99  call    cs:__imp_LocalFree
0x180078c9f  test    r14, r14
0x180078ca2  jz      short loc_180078CAD
0x180078ca4  mov     rcx, r14; hMem
  ... truncated ...
```
