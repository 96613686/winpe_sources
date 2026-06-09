# CProcessInformation::LookupMinClrVersion(void)

- ea: `0x14001de2c`
- end: `0x14001e0fe`
- name: `?LookupMinClrVersion@CProcessInformation@@AEAAJXZ`
- size: `722`
- prototype: `__int64 __fastcall(CProcessInformation *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14001cf1c`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x1400101a8`
- `0x140014f14`
- `0x14001de2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001df4b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001df4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001def7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e07a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001def7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e07a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001e0d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001e0d0`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x14001e062`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x14001e062`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x14001dee7`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x14001dee7`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14001deb9`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14001deb9`

## string_xrefs

- `0x14001de77`: `mscorwks.dll`
- `0x14001de83`: `mscorsvr.dll`
- `0x14001de8f`: `clr.dll`
- `0x14001de9b`: `coreclr.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProcessInformation::LookupMinClrVersion(CProcessInformation *this)
{
  HANDLE Toolhelp32Snapshot; // rax
  void *v3; // rdi
  unsigned __int64 v4; // r14
  __int64 v5; // r8
  signed int v6; // eax
  unsigned int v7; // ebx
  CUserModeHangReport *v8; // rcx
  __int64 v9; // rdx
  __int64 i; // rbx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rax
  MODULEENTRY32W *p_me; // rcx
  _OWORD *v14; // rax
  __int64 v15; // rdx
  signed int LastError; // eax
  _QWORD v18[4]; // [rsp+30h] [rbp-D0h]
  __int128 v19; // [rsp+50h] [rbp-B0h]
  __int128 v20; // [rsp+60h] [rbp-A0h]
  __int128 v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+80h] [rbp-80h]
  __int64 v23; // [rsp+88h] [rbp-78h]
  _BYTE v24[1088]; // [rsp+90h] [rbp-70h] BYREF
  MODULEENTRY32W me; // [rsp+4D0h] [rbp+3D0h] BYREF

  v23 = 0;
  memset_0(&me, 0, sizeof(me));
  v18[0] = L"mscorwks.dll";
  v18[1] = L"mscorsvr.dll";
  v18[2] = L"clr.dll";
  v18[3] = L"coreclr.dll";
  *((_QWORD *)this + 232) = 0;
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(8u, *(_DWORD *)this);
  v3 = Toolhelp32Snapshot;
  v4 = (unsigned __int64)Toolhelp32Snapshot + 1;
  if ( (unsigned __int64)Toolhelp32Snapshot + 1 <= 1 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 89;
      goto LABEL_24;
    }
  }
  else
  {
    me.dwSize = 1080;
    if ( Module32FirstW(Toolhelp32Snapshot, &me) )
    {
      do
      {
        for ( i = 0; i != 4; ++i )
        {
          if ( !(unsigned int)_o__wcsicmp(me.szModule, v18[i], v5) )
          {
            v19 = 0;
            v20 = 0;
            v21 = 0;
            v22 = 0;
            if ( (int)UtilGetFileInfo(me.szExePath, 0) >= 0 )
            {
              v11 = HIDWORD(v19) | ((unsigned __int64)DWORD2(v19) << 32);
              v12 = *((_QWORD *)this + 232);
              if ( !v12 || v11 < v12 )
                *((_QWORD *)this + 232) = v11;
            }
          }
        }
        memset_0(v24, 0, 0x438u);
        p_me = &me;
        v14 = v24;
        v15 = 8;
        do
        {
          *(_OWORD *)&p_me->dwSize = *v14;
          *(_OWORD *)&p_me->ProccntUsage = v14[1];
          *(_OWORD *)&p_me->modBaseSize = v14[2];
          *(_OWORD *)p_me->szModule = v14[3];
          *(_OWORD *)&p_me->szModule[8] = v14[4];
          *(_OWORD *)&p_me->szModule[16] = v14[5];
          *(_OWORD *)&p_me->szModule[24] = v14[6];
          *(_OWORD *)&p_me->szModule[32] = v14[7];
          p_me = (MODULEENTRY32W *)((char *)p_me + 128);
          v14 += 8;
          --v15;
        }
        while ( v15 );
        *(_OWORD *)&p_me->dwSize = *v14;
        *(_OWORD *)&p_me->ProccntUsage = v14[1];
        *(_OWORD *)&p_me->modBaseSize = v14[2];
        *(_QWORD *)p_me->szModule = *((_QWORD *)v14 + 6);
        me.dwSize = 1080;
      }
      while ( Module32NextW(v3, &me) );
      v7 = 0;
    }
    else
    {
      v6 = GetLastError();
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 90;
LABEL_24:
        WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v7);
      }
    }
  }
  if ( v4 > 1 )
    CloseHandle(v3);
  return v7;
}

```

## disassembly

```asm
0x14001de2c  push    rbp
0x14001de2e  push    rbx
0x14001de2f  push    rsi
0x14001de30  push    rdi
0x14001de31  push    r12
0x14001de33  push    r14
0x14001de35  lea     rbp, [rsp-828h]
0x14001de3d  sub     rsp, 928h
0x14001de44  mov     rax, cs:__security_cookie
0x14001de4b  xor     rax, rsp
0x14001de4e  mov     [rbp+850h+var_40], rax
0x14001de55  mov     rsi, rcx
0x14001de58  mov     [rbp+850h+var_8C8], 0
0x14001de60  mov     r12d, 438h
0x14001de66  mov     r8d, r12d; Size
0x14001de69  xor     edx, edx; Val
0x14001de6b  lea     rcx, [rbp+850h+me]; void *
0x14001de72  call    memset_0
0x14001de77  lea     rax, aMscorwksDll; "mscorwks.dll"
0x14001de7e  mov     [rsp+950h+var_920], rax
0x14001de83  lea     rax, aMscorsvrDll; "mscorsvr.dll"
0x14001de8a  mov     [rsp+950h+var_918], rax
0x14001de8f  lea     rax, aClrDll; "clr.dll"
0x14001de96  mov     [rsp+950h+var_910], rax
0x14001de9b  lea     rax, aCoreclrDll; "coreclr.dll"
0x14001dea2  mov     [rsp+950h+var_908], rax
0x14001dea7  mov     qword ptr [rsi+740h], 0
0x14001deb2  mov     edx, [rsi]; th32ProcessID
0x14001deb4  mov     ecx, 8; dwFlags
0x14001deb9  call    cs:__imp_CreateToolhelp32Snapshot
0x14001dec0  nop     dword ptr [rax+rax+00h]
0x14001dec5  mov     rdi, rax
0x14001dec8  lea     r14, [rax+1]
0x14001decc  cmp     r14, 1
0x14001ded0  jbe     loc_14001E07A
0x14001ded6  mov     [rbp+850h+me.dwSize], r12d
0x14001dedd  lea     rdx, [rbp+850h+me]; lpme
0x14001dee4  mov     rcx, rax; hSnapshot
0x14001dee7  call    cs:__imp_Module32FirstW
0x14001deee  nop     dword ptr [rax+rax+00h]
0x14001def3  test    eax, eax
0x14001def5  jnz     short loc_14001DF3D
0x14001def7  call    cs:__imp_GetLastError
0x14001defe  nop     dword ptr [rax+rax+00h]
0x14001df03  mov     ebx, eax
0x14001df05  test    eax, eax
0x14001df07  jle     short loc_14001DF12
0x14001df09  movzx   ebx, ax
0x14001df0c  or      ebx, 80070000h
0x14001df12  lea     rax, WPP_GLOBAL_Control
0x14001df19  mov     rcx, cs:WPP_GLOBAL_Control
0x14001df20  cmp     rcx, rax
0x14001df23  jz      loc_14001E0C7
0x14001df29  test    byte ptr [rcx+1Ch], 1
0x14001df2d  jz      loc_14001E0C7
0x14001df33  mov     edx, 5Ah ; 'Z'
0x14001df38  jmp     loc_14001E0B3
0x14001df3d  xor     ebx, ebx
0x14001df3f  mov     rdx, [rsp+rbx*8+950h+var_920]
0x14001df44  lea     rcx, [rbp+850h+me.szModule]
0x14001df4b  call    cs:__imp__o__wcsicmp
0x14001df52  nop     dword ptr [rax+rax+00h]
0x14001df57  test    eax, eax
0x14001df59  jnz     short loc_14001DFB8
0x14001df5b  xorps   xmm0, xmm0
0x14001df5e  xor     eax, eax
0x14001df60  movups  [rsp+950h+var_900], xmm0
0x14001df65  movups  [rsp+950h+var_8F0], xmm0
0x14001df6a  movups  [rsp+950h+var_8E0], xmm0
0x14001df6f  mov     [rbp+850h+var_8D0], eax
0x14001df72  mov     [rsp+950h+var_930], eax; int
0x14001df76  xor     r9d, r9d
0x14001df79  xor     r8d, r8d
0x14001df7c  lea     rdx, [rsp+950h+var_900]
0x14001df81  lea     rcx, [rbp+850h+me.szExePath]; lpwstrFilename
0x14001df88  call    ?UtilGetFileInfo@@YAJPEB_WPEAUtagVS_FIXEDFILEINFO@@QEBQEB_WQEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@K@Z; UtilGetFileInfo(wchar_t const *,tagVS_FIXEDFILEINFO *,wchar_t const * const * const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> * const,ulong)
0x14001df8d  test    eax, eax
0x14001df8f  js      short loc_14001DFB8
0x14001df91  mov     ecx, dword ptr [rsp+950h+var_900+8]
0x14001df95  shl     rcx, 20h
0x14001df99  mov     eax, dword ptr [rsp+950h+var_900+0Ch]
0x14001df9d  or      rcx, rax
0x14001dfa0  mov     rax, [rsi+740h]
0x14001dfa7  test    rax, rax
0x14001dfaa  jz      short loc_14001DFB1
0x14001dfac  cmp     rcx, rax
0x14001dfaf  jnb     short loc_14001DFB8
0x14001dfb1  mov     [rsi+740h], rcx
0x14001dfb8  inc     rbx
0x14001dfbb  cmp     rbx, 4
0x14001dfbf  jnz     loc_14001DF3F
0x14001dfc5  mov     r8, r12; Size
0x14001dfc8  xor     edx, edx; Val
0x14001dfca  lea     rcx, [rbp+850h+var_8C0]; void *
0x14001dfce  call    memset_0
0x14001dfd3  lea     rcx, [rbp+850h+me]
0x14001dfda  lea     rax, [rbp+850h+var_8C0]
0x14001dfde  lea     edx, [rbx+4]
0x14001dfe1  movups  xmm0, xmmword ptr [rax]
0x14001dfe4  movups  xmmword ptr [rcx], xmm0
0x14001dfe7  movups  xmm1, xmmword ptr [rax+10h]
0x14001dfeb  movups  xmmword ptr [rcx+10h], xmm1
0x14001dfef  movups  xmm0, xmmword ptr [rax+20h]
0x14001dff3  movups  xmmword ptr [rcx+20h], xmm0
0x14001dff7  movups  xmm1, xmmword ptr [rax+30h]
0x14001dffb  movups  xmmword ptr [rcx+30h], xmm1
0x14001dfff  movups  xmm0, xmmword ptr [rax+40h]
0x14001e003  movups  xmmword ptr [rcx+40h], xmm0
0x14001e007  movups  xmm1, xmmword ptr [rax+50h]
0x14001e00b  movups  xmmword ptr [rcx+50h], xmm1
0x14001e00f  movups  xmm0, xmmword ptr [rax+60h]
0x14001e013  movups  xmmword ptr [rcx+60h], xmm0
0x14001e017  movups  xmm1, xmmword ptr [rax+70h]
0x14001e01b  movups  xmmword ptr [rcx+70h], xmm1
0x14001e01f  lea     rcx, [rcx+80h]
0x14001e026  lea     rax, [rax+80h]
0x14001e02d  sub     rdx, 1
0x14001e031  jnz     short loc_14001DFE1
0x14001e033  movups  xmm0, xmmword ptr [rax]
0x14001e036  movups  xmmword ptr [rcx], xmm0
0x14001e039  movups  xmm1, xmmword ptr [rax+10h]
0x14001e03d  movups  xmmword ptr [rcx+10h], xmm1
0x14001e041  movups  xmm0, xmmword ptr [rax+20h]
0x14001e045  movups  xmmword ptr [rcx+20h], xmm0
0x14001e049  mov     rax, [rax+30h]
0x14001e04d  mov     [rcx+30h], rax
0x14001e051  mov     [rbp+850h+me.dwSize], r12d
0x14001e058  lea     rdx, [rbp+850h+me]; lpme
0x14001e05f  mov     rcx, rdi; hSnapshot
0x14001e062  call    cs:__imp_Module32NextW
0x14001e069  nop     dword ptr [rax+rax+00h]
0x14001e06e  test    eax, eax
0x14001e070  jnz     loc_14001DF3D
0x14001e076  xor     ebx, ebx
0x14001e078  jmp     short loc_14001E0C7
0x14001e07a  call    cs:__imp_GetLastError
0x14001e081  nop     dword ptr [rax+rax+00h]
0x14001e086  mov     ebx, eax
0x14001e088  test    eax, eax
0x14001e08a  jle     short loc_14001E095
0x14001e08c  movzx   ebx, ax
0x14001e08f  or      ebx, 80070000h
0x14001e095  lea     rax, WPP_GLOBAL_Control
0x14001e09c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e0a3  cmp     rcx, rax
0x14001e0a6  jz      short loc_14001E0C7
0x14001e0a8  test    byte ptr [rcx+1Ch], 1
0x14001e0ac  jz      short loc_14001E0C7
0x14001e0ae  mov     edx, 59h ; 'Y'
0x14001e0b3  mov     r9d, ebx
0x14001e0b6  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001e0bd  mov     rcx, [rcx+10h]
0x14001e0c1  call    WPP_SF_d
0x14001e0c6  nop
0x14001e0c7  cmp     r14, 1
0x14001e0cb  jbe     short loc_14001E0DC
0x14001e0cd  mov     rcx, rdi; hObject
0x14001e0d0  call    cs:__imp_CloseHandle
0x14001e0d7  nop     dword ptr [rax+rax+00h]
0x14001e0dc  mov     eax, ebx
0x14001e0de  mov     rcx, [rbp+850h+var_40]
0x14001e0e5  xor     rcx, rsp; StackCookie
0x14001e0e8  call    __security_check_cookie
0x14001e0ed  add     rsp, 928h
0x14001e0f4  pop     r14
0x14001e0f6  pop     r12
0x14001e0f8  pop     rdi
0x14001e0f9  pop     rsi
0x14001e0fa  pop     rbx
0x14001e0fb  pop     rbp
0x14001e0fc  retn
```
