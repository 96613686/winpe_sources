# CTieredVolume::UpdateTieringInformationFromVolume(void *,bool)

- ea: `0x140016d18`
- end: `0x140017117`
- name: `?UpdateTieringInformationFromVolume@CTieredVolume@@AEAAJPEAX_N@Z`
- size: `1023`
- prototype: `__int64 __fastcall(CTieredVolume *this, HANDLE hDevice)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1400127dc`

## callees

- `0x140002db0`
- `0x140004ef0`
- `0x140005420`
- `0x14000b7f8`
- `0x1400166f4`
- `0x140016a44`
- `0x140016d18`
- `0x140017ee8`
- `0x14003fbb0`

## import_xrefs

- `msvcrt!malloc` at `0x140016d95`
- `msvcrt!malloc` at `0x140016eac`
- `msvcrt!malloc` at `0x140016d95`
- `msvcrt!malloc` at `0x140016eac`
- `msvcrt!free` at `0x140016e05`
- `msvcrt!free` at `0x140016f21`
- `msvcrt!free` at `0x140016f9c`
- `msvcrt!free` at `0x140016fa7`
- `msvcrt!free` at `0x140016fc1`
- `msvcrt!free` at `0x14001703c`
- `msvcrt!free` at `0x14001704a`
- `msvcrt!free` at `0x140016e05`
- `msvcrt!free` at `0x140016f21`
- `msvcrt!free` at `0x140016f9c`
- `msvcrt!free` at `0x140016fa7`
- `msvcrt!free` at `0x140016fc1`
- `msvcrt!free` at `0x14001703c`
- `msvcrt!free` at `0x14001704a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016ddb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016ef6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017050`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016ddb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016ef6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017050`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140016dd1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140016eec`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140016dd1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140016eec`

## string_xrefs

- `0x140016d5b`: `CTieredVolume::UpdateTieringInformationFromVolume`

## pseudocode

```c
__int64 __fastcall CTieredVolume::UpdateTieringInformationFromVolume(CTieredVolume *this, HANDLE hDevice)
{
  unsigned int *lpOutBuffer; // rbx
  DWORD v5; // r15d
  DWORD nOutBufferSize; // r14d
  int v7; // edi
  DWORD LastError; // eax
  __int64 v9; // r8
  void *v10; // rbx
  int v11; // r14d
  DWORD v12; // eax
  unsigned int v14; // eax
  unsigned int v15; // ebx
  DWORD v16; // eax
  unsigned int v17; // eax
  int v18; // r8d
  DWORD BytesReturned; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v20[8]; // [rsp+48h] [rbp-21h] BYREF
  int v21; // [rsp+50h] [rbp-19h]
  void *v22; // [rsp+58h] [rbp-11h] BYREF
  void *Block[3]; // [rsp+60h] [rbp-9h] BYREF
  _DWORD InBuffer[2]; // [rsp+78h] [rbp+Fh] BYREF
  __int128 v25; // [rsp+80h] [rbp+17h]
  __int64 v26; // [rsp+90h] [rbp+27h]

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieredVolume::UpdateTieringInformationFromVolume";
  CHResultImp::CHResultImp((CHResultImp *)v20);
  lpOutBuffer = 0;
  BytesReturned = 0;
  v5 = 0x2000;
  nOutBufferSize = 0x2000;
  v7 = 122;
  while ( v7 == 122 || v7 == 234 )
  {
    lpOutBuffer = (unsigned int *)malloc(nOutBufferSize);
    if ( !lpOutBuffer )
    {
      v15 = -2147024882;
      v21 = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          135,
          (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          (_DWORD)this + 672,
          14);
      }
      goto LABEL_53;
    }
    if ( DeviceIoControl(hDevice, 0x902ECu, 0, 0, lpOutBuffer, nOutBufferSize, &BytesReturned, 0) )
    {
      v7 = 0;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError != 122 && LastError != 234 )
      {
        free(lpOutBuffer);
        v16 = GetLastError();
        v17 = ATL::AtlHresultFromWin32(v16);
        v15 = v17;
        v21 = v17;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, v18, (_DWORD)this + 672, v17);
        }
LABEL_53:
        CHResultImp::~CHResultImp((CHResultImp *)v20);
        return v15;
      }
      nOutBufferSize *= 2;
      if ( BytesReturned > nOutBufferSize )
        nOutBufferSize = BytesReturned;
      free(lpOutBuffer);
      lpOutBuffer = 0;
    }
  }
  v22 = lpOutBuffer;
  Block[1] = &v22;
  v9 = lpOutBuffer[4];
  if ( (unsigned int)v9 < 2 && *((_QWORD *)this + 6) == v9 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, v9, (_DWORD)this + 672, lpOutBuffer[4]);
    }
  }
  else
  {
    CTieredVolume::UpdateTierTraitsListFromFsctlResponse(
      this,
      (struct _FSCTL_QUERY_STORAGE_CLASSES_OUTPUT *)lpOutBuffer);
  }
  v10 = 0;
  v25 = 0;
  v26 = 0;
  InBuffer[1] = 32;
  InBuffer[0] = 32;
  v11 = 122;
  while ( v11 == 122 || v11 == 234 )
  {
    v10 = malloc(v5);
    if ( !v10 )
    {
      v15 = -2147024882;
      v21 = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          138,
          (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          (_DWORD)this + 672,
          14);
      }
      goto LABEL_44;
    }
    if ( DeviceIoControl(hDevice, 0x902F0u, InBuffer, 0x20u, v10, v5, &BytesReturned, 0) )
    {
      v11 = 0;
    }
    else
    {
      v12 = GetLastError();
      v11 = v12;
      if ( v12 != 122 && v12 != 234 )
      {
        free(v10);
        v14 = ATL::AtlHresultFromWin32(v11);
        v15 = v14;
        v21 = v14;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Zd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            139,
            (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
            (_DWORD)this + 672,
            v14);
        }
LABEL_44:
        free(v22);
        goto LABEL_53;
      }
      v5 *= 2;
      if ( BytesReturned > v5 )
        v5 = BytesReturned;
      free(v10);
      v10 = 0;
    }
  }
  Block[0] = v10;
  Block[2] = Block;
  *((_QWORD *)this + 17) = *((_QWORD *)v10 + 2);
  if ( *((_DWORD *)v10 + 7) < 2u
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, v9, (_DWORD)this + 672, *((_DWORD *)v10 + 7));
  }
  CTieredVolume::UpdateTierRegionsListFromFsctlResponse(this, (struct _FSCTL_QUERY_REGION_INFO_OUTPUT *)v10);
  v21 = 0;
  free(Block[0]);
  free(v22);
  CHResultImp::~CHResultImp((CHResultImp *)v20);
  return 0;
}

```

## disassembly

```asm
0x140016d18  mov     [rsp-8+arg_10], rbx
0x140016d1d  mov     [rsp-8+arg_18], rsi
0x140016d22  push    rbp
0x140016d23  push    rdi
0x140016d24  push    r12
0x140016d26  push    r14
0x140016d28  push    r15
0x140016d2a  lea     rbp, [rsp-37h]
0x140016d2f  sub     rsp, 0A0h
0x140016d36  mov     rax, cs:__security_cookie
0x140016d3d  xor     rax, rsp
0x140016d40  mov     [rbp+57h+var_28], rax
0x140016d44  mov     r12, rdx
0x140016d47  mov     rsi, rcx
0x140016d4a  mov     edx, 8
0x140016d4f  mov     rax, gs:58h
0x140016d58  mov     rcx, [rax]
0x140016d5b  lea     rax, aCtieredvolumeU; "CTieredVolume::UpdateTieringInformation"...
0x140016d62  mov     [rdx+rcx], rax
0x140016d66  lea     rcx, [rbp+57h+var_78]; this
0x140016d6a  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140016d6f  nop
0x140016d70  xor     ebx, ebx
0x140016d72  mov     [rbp+57h+BytesReturned], ebx
0x140016d75  mov     r15d, 2000h
0x140016d7b  mov     r14d, r15d
0x140016d7e  lea     edi, [rbx+7Ah]
0x140016d81  cmp     edi, 7Ah ; 'z'
0x140016d84  jz      short loc_140016D92
0x140016d86  cmp     edi, 0EAh
0x140016d8c  jnz     loc_140016E19
0x140016d92  mov     ecx, r14d; Size
0x140016d95  call    cs:__imp_malloc
0x140016d9b  mov     rbx, rax
0x140016d9e  test    rax, rax
0x140016da1  jz      loc_14001709C
0x140016da7  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x140016db0  lea     rax, [rbp+57h+BytesReturned]
0x140016db4  mov     [rsp+0C0h+lpBytesReturned], rax; lpBytesReturned
0x140016db9  mov     [rsp+0C0h+nOutBufferSize], r14d; nOutBufferSize
0x140016dbe  mov     [rsp+0C0h+lpOutBuffer], rbx; lpOutBuffer
0x140016dc3  xor     r9d, r9d; nInBufferSize
0x140016dc6  xor     r8d, r8d; lpInBuffer
0x140016dc9  mov     edx, 902ECh; dwIoControlCode
0x140016dce  mov     rcx, r12; hDevice
0x140016dd1  call    cs:__imp_DeviceIoControl
0x140016dd7  test    eax, eax
0x140016dd9  jnz     short loc_140016E12
0x140016ddb  call    cs:__imp_GetLastError
0x140016de1  mov     edi, eax
0x140016de3  cmp     eax, 7Ah ; 'z'
0x140016de6  jz      short loc_140016DF3
0x140016de8  cmp     eax, 0EAh
0x140016ded  jnz     loc_140017047
0x140016df3  lea     ecx, [r14+r14]
0x140016df7  mov     r14d, ecx
0x140016dfa  cmp     [rbp+57h+BytesReturned], ecx
0x140016dfd  cmova   r14d, [rbp+57h+BytesReturned]
0x140016e02  mov     rcx, rbx; Block
0x140016e05  call    cs:__imp_free
0x140016e0b  xor     ebx, ebx
0x140016e0d  jmp     loc_140016D81
0x140016e12  xor     edi, edi
0x140016e14  jmp     loc_140016D81
0x140016e19  mov     [rbp+57h+var_68], rbx
0x140016e1d  lea     rax, [rbp+57h+var_68]
0x140016e21  mov     [rbp+57h+var_58], rax
0x140016e25  mov     r8d, [rbx+10h]
0x140016e29  lea     rdi, WPP_GLOBAL_Control
0x140016e30  cmp     r8d, 2
0x140016e34  jnb     short loc_140016E70
0x140016e36  cmp     [rsi+30h], r8
0x140016e3a  jnz     short loc_140016E70
0x140016e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140016e43  cmp     rcx, rdi
0x140016e46  jz      short loc_140016E7B
0x140016e48  test    byte ptr [rcx+1Ch], 1
0x140016e4c  jz      short loc_140016E7B
0x140016e4e  cmp     byte ptr [rcx+19h], 4
0x140016e52  jb      short loc_140016E7B
0x140016e54  lea     r9, [rsi+2A0h]
0x140016e5b  mov     edx, 89h
0x140016e60  mov     dword ptr [rsp+0C0h+lpOutBuffer], r8d
0x140016e65  mov     rcx, [rcx+10h]
0x140016e69  call    WPP_SF_ZD
0x140016e6e  jmp     short loc_140016E7B
0x140016e70  mov     rdx, rbx; struct _FSCTL_QUERY_STORAGE_CLASSES_OUTPUT *
0x140016e73  mov     rcx, rsi; this
0x140016e76  call    ?UpdateTierTraitsListFromFsctlResponse@CTieredVolume@@AEAAXPEAU_FSCTL_QUERY_STORAGE_CLASSES_OUTPUT@@@Z; CTieredVolume::UpdateTierTraitsListFromFsctlResponse(_FSCTL_QUERY_STORAGE_CLASSES_OUTPUT *)
0x140016e7b  xor     ebx, ebx
0x140016e7d  xorps   xmm0, xmm0
0x140016e80  movdqu  [rbp+57h+var_40], xmm0
0x140016e85  mov     [rbp+57h+var_30], rbx
0x140016e89  lea     eax, [rbx+20h]
0x140016e8c  mov     [rbp+57h+var_44], eax
0x140016e8f  mov     [rbp+57h+InBuffer], eax
0x140016e92  lea     r14d, [rbx+7Ah]
0x140016e96  cmp     r14d, 7Ah ; 'z'
0x140016e9a  jz      short loc_140016EA9
0x140016e9c  cmp     r14d, 0EAh
0x140016ea3  jnz     loc_140016F36
0x140016ea9  mov     ecx, r15d; Size
0x140016eac  call    cs:__imp_malloc
0x140016eb2  mov     rbx, rax
0x140016eb5  test    rax, rax
0x140016eb8  jz      loc_140016FF7
0x140016ebe  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x140016ec7  lea     rax, [rbp+57h+BytesReturned]
0x140016ecb  mov     [rsp+0C0h+lpBytesReturned], rax; lpBytesReturned
0x140016ed0  mov     [rsp+0C0h+nOutBufferSize], r15d; nOutBufferSize
0x140016ed5  mov     [rsp+0C0h+lpOutBuffer], rbx; lpOutBuffer
0x140016eda  mov     r9d, 20h ; ' '; nInBufferSize
0x140016ee0  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x140016ee4  mov     edx, 902F0h; dwIoControlCode
0x140016ee9  mov     rcx, r12; hDevice
0x140016eec  call    cs:__imp_DeviceIoControl
0x140016ef2  test    eax, eax
0x140016ef4  jnz     short loc_140016F2E
0x140016ef6  call    cs:__imp_GetLastError
0x140016efc  mov     r14d, eax
0x140016eff  cmp     eax, 7Ah ; 'z'
0x140016f02  jz      short loc_140016F0F
0x140016f04  cmp     eax, 0EAh
0x140016f09  jnz     loc_140016FBE
0x140016f0f  lea     ecx, [r15+r15]
0x140016f13  mov     r15d, ecx
0x140016f16  cmp     [rbp+57h+BytesReturned], ecx
0x140016f19  cmova   r15d, [rbp+57h+BytesReturned]
0x140016f1e  mov     rcx, rbx; Block
0x140016f21  call    cs:__imp_free
0x140016f27  xor     ebx, ebx
0x140016f29  jmp     loc_140016E96
0x140016f2e  xor     r14d, r14d
0x140016f31  jmp     loc_140016E96
0x140016f36  mov     [rbp+57h+Block], rbx
0x140016f3a  lea     rax, [rbp+57h+Block]
0x140016f3e  mov     [rbp+57h+var_50], rax
0x140016f42  mov     rax, [rbx+10h]
0x140016f46  mov     [rsi+88h], rax
0x140016f4d  mov     eax, [rbx+1Ch]
0x140016f50  cmp     eax, 2
0x140016f53  jnb     short loc_140016F86
0x140016f55  mov     rcx, cs:WPP_GLOBAL_Control
0x140016f5c  cmp     rcx, rdi
0x140016f5f  jz      short loc_140016F86
0x140016f61  test    byte ptr [rcx+1Ch], 1
0x140016f65  jz      short loc_140016F86
0x140016f67  cmp     byte ptr [rcx+19h], 4
0x140016f6b  jb      short loc_140016F86
0x140016f6d  lea     r9, [rsi+2A0h]
0x140016f74  mov     edx, 8Ch
0x140016f79  mov     dword ptr [rsp+0C0h+lpOutBuffer], eax
0x140016f7d  mov     rcx, [rcx+10h]
0x140016f81  call    WPP_SF_ZD
0x140016f86  mov     rdx, rbx; struct _FSCTL_QUERY_REGION_INFO_OUTPUT *
0x140016f89  mov     rcx, rsi; this
0x140016f8c  call    ?UpdateTierRegionsListFromFsctlResponse@CTieredVolume@@AEAAXPEAU_FSCTL_QUERY_REGION_INFO_OUTPUT@@@Z; CTieredVolume::UpdateTierRegionsListFromFsctlResponse(_FSCTL_QUERY_REGION_INFO_OUTPUT *)
0x140016f91  mov     [rbp+57h+var_70], 0
0x140016f98  mov     rcx, [rbp+57h+Block]; Block
0x140016f9c  call    cs:__imp_free
0x140016fa2  nop
0x140016fa3  mov     rcx, [rbp+57h+var_68]; Block
0x140016fa7  call    cs:__imp_free
0x140016fad  nop
0x140016fae  lea     rcx, [rbp+57h+var_78]; this
0x140016fb2  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x140016fb7  xor     eax, eax
0x140016fb9  jmp     loc_1400170EF
0x140016fbe  mov     rcx, rbx; Block
0x140016fc1  call    cs:__imp_free
0x140016fc7  mov     ecx, r14d; unsigned int
0x140016fca  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140016fcf  mov     ebx, eax
0x140016fd1  mov     [rbp+57h+var_70], eax
0x140016fd4  mov     rcx, cs:WPP_GLOBAL_Control
0x140016fdb  cmp     rcx, rdi
0x140016fde  jz      short loc_140017038
0x140016fe0  test    byte ptr [rcx+1Ch], 1
0x140016fe4  jz      short loc_140017038
0x140016fe6  cmp     byte ptr [rcx+19h], 2
0x140016fea  jb      short loc_140017038
0x140016fec  mov     edx, 8Bh
0x140016ff1  mov     dword ptr [rsp+0C0h+lpOutBuffer], eax
0x140016ff5  jmp     short loc_140017020
0x140016ff7  mov     ebx, 8007000Eh
0x140016ffc  mov     [rbp+57h+var_70], ebx
0x140016fff  mov     rcx, cs:WPP_GLOBAL_Control
0x140017006  cmp     rcx, rdi
0x140017009  jz      short loc_140017038
0x14001700b  test    byte ptr [rcx+1Ch], 1
0x14001700f  jz      short loc_140017038
0x140017011  cmp     byte ptr [rcx+19h], 2
0x140017015  jb      short loc_140017038
0x140017017  mov     edx, 8Ah
0x14001701c  mov     dword ptr [rsp+0C0h+lpOutBuffer], ebx
0x140017020  lea     r9, [rsi+2A0h]
0x140017027  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14001702e  mov     rcx, [rcx+10h]
0x140017032  call    WPP_SF_Zd
0x140017037  nop
0x140017038  mov     rcx, [rbp+57h+var_68]; Block
0x14001703c  call    cs:__imp_free
0x140017042  jmp     loc_1400170E4
0x140017047  mov     rcx, rbx; Block
0x14001704a  call    cs:__imp_free
0x140017050  call    cs:__imp_GetLastError
0x140017056  mov     ecx, eax; unsigned int
0x140017058  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001705d  mov     ebx, eax
0x14001705f  mov     [rbp+57h+var_70], eax
0x140017062  lea     rdi, WPP_GLOBAL_Control
0x140017069  mov     rcx, cs:WPP_GLOBAL_Control
0x140017070  cmp     rcx, rdi
0x140017073  jz      short loc_1400170E4
0x140017075  test    byte ptr [rcx+1Ch], 1
0x140017079  jz      short loc_1400170E4
0x14001707b  cmp     byte ptr [rcx+19h], 4
0x14001707f  jb      short loc_1400170E4
0x140017081  lea     r9, [rsi+2A0h]
0x140017088  mov     edx, 88h
0x14001708d  mov     dword ptr [rsp+0C0h+lpOutBuffer], eax
0x140017091  mov     rcx, [rcx+10h]
0x140017095  call    WPP_SF_ZD
0x14001709a  jmp     short loc_1400170E4
0x14001709c  mov     ebx, 8007000Eh
0x1400170a1  mov     [rbp+57h+var_70], ebx
0x1400170a4  lea     rdi, WPP_GLOBAL_Control
0x1400170ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400170b2  cmp     rcx, rdi
0x1400170b5  jz      short loc_1400170E4
0x1400170b7  test    byte ptr [rcx+1Ch], 1
0x1400170bb  jz      short loc_1400170E4
0x1400170bd  cmp     byte ptr [rcx+19h], 2
0x1400170c1  jb      short loc_1400170E4
0x1400170c3  lea     r9, [rsi+2A0h]
0x1400170ca  mov     edx, 87h
0x1400170cf  mov     dword ptr [rsp+0C0h+lpOutBuffer], ebx
0x1400170d3  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x1400170da  mov     rcx, [rcx+10h]
0x1400170de  call    WPP_SF_Zd
0x1400170e3  nop
0x1400170e4  lea     rcx, [rbp+57h+var_78]; this
0x1400170e8  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1400170ed  mov     eax, ebx
0x1400170ef  mov     rcx, [rbp+57h+var_28]
0x1400170f3  xor     rcx, rsp; StackCookie
0x1400170f6  call    __security_check_cookie
0x1400170fb  lea     r11, [rsp+0C0h+var_20]
0x140017103  mov     rbx, [r11+40h]
0x140017107  mov     rsi, [r11+48h]
0x14001710b  mov     rsp, r11
0x14001710e  pop     r15
0x140017110  pop     r14
0x140017112  pop     r12
0x140017114  pop     rdi
0x140017115  pop     rbp
0x140017116  retn
```
