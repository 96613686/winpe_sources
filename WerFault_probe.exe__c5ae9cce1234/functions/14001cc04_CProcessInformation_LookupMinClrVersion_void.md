# CProcessInformation::LookupMinClrVersion(void)

- ea: `0x14001cc04`
- end: `0x14001cea7`
- name: `?LookupMinClrVersion@CProcessInformation@@AEAAJXZ`
- size: `675`
- prototype: `__int64 __fastcall(CProcessInformation *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14001bdbc`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x14000fb60`
- `0x140014474`
- `0x14001cc04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001cd11`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001cd11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ccc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ce30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ccc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ce30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ce80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ce80`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x14001ce1e`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x14001ce1e`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x14001ccb9`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x14001ccb9`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14001cc91`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14001cc91`

## string_xrefs

- `0x14001cc4f`: `mscorwks.dll`
- `0x14001cc5b`: `mscorsvr.dll`
- `0x14001cc67`: `clr.dll`
- `0x14001cc73`: `coreclr.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProcessInformation::LookupMinClrVersion(CProcessInformation *this)
{
  HANDLE Toolhelp32Snapshot; // rax
  void *v3; // rdi
  unsigned __int64 v4; // r14
  signed int v5; // eax
  unsigned int v6; // ebx
  CUserModeHangReport *v7; // rcx
  __int64 v8; // rdx
  __int64 i; // rbx
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  MODULEENTRY32W *p_me; // rcx
  _OWORD *v13; // rax
  __int64 v14; // rdx
  signed int LastError; // eax
  _QWORD v17[4]; // [rsp+30h] [rbp-D0h]
  __int128 v18; // [rsp+50h] [rbp-B0h]
  __int128 v19; // [rsp+60h] [rbp-A0h]
  __int128 v20; // [rsp+70h] [rbp-90h]
  int v21; // [rsp+80h] [rbp-80h]
  __int64 v22; // [rsp+88h] [rbp-78h]
  _BYTE v23[1088]; // [rsp+90h] [rbp-70h] BYREF
  MODULEENTRY32W me; // [rsp+4D0h] [rbp+3D0h] BYREF

  v22 = 0;
  memset_0(&me, 0, sizeof(me));
  v17[0] = L"mscorwks.dll";
  v17[1] = L"mscorsvr.dll";
  v17[2] = L"clr.dll";
  v17[3] = L"coreclr.dll";
  *((_QWORD *)this + 232) = 0;
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(8u, *(_DWORD *)this);
  v3 = Toolhelp32Snapshot;
  v4 = (unsigned __int64)Toolhelp32Snapshot + 1;
  if ( (unsigned __int64)Toolhelp32Snapshot + 1 <= 1 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 89;
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
          if ( !(unsigned int)_o__wcsicmp(me.szModule, v17[i]) )
          {
            v18 = 0;
            v19 = 0;
            v20 = 0;
            v21 = 0;
            if ( (int)UtilGetFileInfo(me.szExePath, 0) >= 0 )
            {
              v10 = HIDWORD(v18) | ((unsigned __int64)DWORD2(v18) << 32);
              v11 = *((_QWORD *)this + 232);
              if ( !v11 || v10 < v11 )
                *((_QWORD *)this + 232) = v10;
            }
          }
        }
        memset_0(v23, 0, 0x438u);
        p_me = &me;
        v13 = v23;
        v14 = 8;
        do
        {
          *(_OWORD *)&p_me->dwSize = *v13;
          *(_OWORD *)&p_me->ProccntUsage = v13[1];
          *(_OWORD *)&p_me->modBaseSize = v13[2];
          *(_OWORD *)p_me->szModule = v13[3];
          *(_OWORD *)&p_me->szModule[8] = v13[4];
          *(_OWORD *)&p_me->szModule[16] = v13[5];
          *(_OWORD *)&p_me->szModule[24] = v13[6];
          *(_OWORD *)&p_me->szModule[32] = v13[7];
          p_me = (MODULEENTRY32W *)((char *)p_me + 128);
          v13 += 8;
          --v14;
        }
        while ( v14 );
        *(_OWORD *)&p_me->dwSize = *v13;
        *(_OWORD *)&p_me->ProccntUsage = v13[1];
        *(_OWORD *)&p_me->modBaseSize = v13[2];
        *(_QWORD *)p_me->szModule = *((_QWORD *)v13 + 6);
        me.dwSize = 1080;
      }
      while ( Module32NextW(v3, &me) );
      v6 = 0;
    }
    else
    {
      v5 = GetLastError();
      v6 = v5;
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 90;
LABEL_24:
        WPP_SF_d(*((_QWORD *)v7 + 2), v8, &WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v6);
      }
    }
  }
  if ( v4 > 1 )
    CloseHandle(v3);
  return v6;
}

```

## disassembly

```asm
0x14001cc04  push    rbp
0x14001cc06  push    rbx
0x14001cc07  push    rsi
0x14001cc08  push    rdi
0x14001cc09  push    r12
0x14001cc0b  push    r14
0x14001cc0d  lea     rbp, [rsp-828h]
0x14001cc15  sub     rsp, 928h
0x14001cc1c  mov     rax, cs:__security_cookie
0x14001cc23  xor     rax, rsp
0x14001cc26  mov     [rbp+850h+var_40], rax
0x14001cc2d  mov     rsi, rcx
0x14001cc30  mov     [rbp+850h+var_8C8], 0
0x14001cc38  mov     r12d, 438h
0x14001cc3e  mov     r8d, r12d; Size
0x14001cc41  xor     edx, edx; Val
0x14001cc43  lea     rcx, [rbp+850h+me]; void *
0x14001cc4a  call    memset_0
0x14001cc4f  lea     rax, aMscorwksDll; "mscorwks.dll"
0x14001cc56  mov     [rsp+950h+var_920], rax
0x14001cc5b  lea     rax, aMscorsvrDll; "mscorsvr.dll"
0x14001cc62  mov     [rsp+950h+var_918], rax
0x14001cc67  lea     rax, aClrDll; "clr.dll"
0x14001cc6e  mov     [rsp+950h+var_910], rax
0x14001cc73  lea     rax, aCoreclrDll; "coreclr.dll"
0x14001cc7a  mov     [rsp+950h+var_908], rax
0x14001cc7f  mov     qword ptr [rsi+740h], 0
0x14001cc8a  mov     edx, [rsi]; th32ProcessID
0x14001cc8c  mov     ecx, 8; dwFlags
0x14001cc91  call    cs:__imp_CreateToolhelp32Snapshot
0x14001cc97  mov     rdi, rax
0x14001cc9a  lea     r14, [rax+1]
0x14001cc9e  cmp     r14, 1
0x14001cca2  jbe     loc_14001CE30
0x14001cca8  mov     [rbp+850h+me.dwSize], r12d
0x14001ccaf  lea     rdx, [rbp+850h+me]; lpme
0x14001ccb6  mov     rcx, rax; hSnapshot
0x14001ccb9  call    cs:__imp_Module32FirstW
0x14001ccbf  test    eax, eax
0x14001ccc1  jnz     short loc_14001CD03
0x14001ccc3  call    cs:__imp_GetLastError
0x14001ccc9  mov     ebx, eax
0x14001cccb  test    eax, eax
0x14001cccd  jle     short loc_14001CCD8
0x14001cccf  movzx   ebx, ax
0x14001ccd2  or      ebx, 80070000h
0x14001ccd8  lea     rax, WPP_GLOBAL_Control
0x14001ccdf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cce6  cmp     rcx, rax
0x14001cce9  jz      loc_14001CE77
0x14001ccef  test    byte ptr [rcx+1Ch], 1
0x14001ccf3  jz      loc_14001CE77
0x14001ccf9  mov     edx, 5Ah ; 'Z'
0x14001ccfe  jmp     loc_14001CE63
0x14001cd03  xor     ebx, ebx
0x14001cd05  mov     rdx, [rsp+rbx*8+950h+var_920]
0x14001cd0a  lea     rcx, [rbp+850h+me.szModule]
0x14001cd11  call    cs:__imp__o__wcsicmp
0x14001cd17  test    eax, eax
0x14001cd19  jnz     short loc_14001CD78
0x14001cd1b  xorps   xmm0, xmm0
0x14001cd1e  xor     eax, eax
0x14001cd20  movups  [rsp+950h+var_900], xmm0
0x14001cd25  movups  [rsp+950h+var_8F0], xmm0
0x14001cd2a  movups  [rsp+950h+var_8E0], xmm0
0x14001cd2f  mov     [rbp+850h+var_8D0], eax
0x14001cd32  mov     [rsp+950h+var_930], eax; int
0x14001cd36  xor     r9d, r9d
0x14001cd39  xor     r8d, r8d
0x14001cd3c  lea     rdx, [rsp+950h+var_900]
0x14001cd41  lea     rcx, [rbp+850h+me.szExePath]; lpwstrFilename
0x14001cd48  call    ?UtilGetFileInfo@@YAJPEB_WPEAUtagVS_FIXEDFILEINFO@@QEBQEB_WQEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@K@Z; UtilGetFileInfo(wchar_t const *,tagVS_FIXEDFILEINFO *,wchar_t const * const * const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> * const,ulong)
0x14001cd4d  test    eax, eax
0x14001cd4f  js      short loc_14001CD78
0x14001cd51  mov     ecx, dword ptr [rsp+950h+var_900+8]
0x14001cd55  shl     rcx, 20h
0x14001cd59  mov     eax, dword ptr [rsp+950h+var_900+0Ch]
0x14001cd5d  or      rcx, rax
0x14001cd60  mov     rax, [rsi+740h]
0x14001cd67  test    rax, rax
0x14001cd6a  jz      short loc_14001CD71
0x14001cd6c  cmp     rcx, rax
0x14001cd6f  jnb     short loc_14001CD78
0x14001cd71  mov     [rsi+740h], rcx
0x14001cd78  inc     rbx
0x14001cd7b  cmp     rbx, 4
0x14001cd7f  jnz     short loc_14001CD05
0x14001cd81  mov     r8, r12; Size
0x14001cd84  xor     edx, edx; Val
0x14001cd86  lea     rcx, [rbp+850h+var_8C0]; void *
0x14001cd8a  call    memset_0
0x14001cd8f  lea     rcx, [rbp+850h+me]
0x14001cd96  lea     rax, [rbp+850h+var_8C0]
0x14001cd9a  lea     edx, [rbx+4]
0x14001cd9d  movups  xmm0, xmmword ptr [rax]
0x14001cda0  movups  xmmword ptr [rcx], xmm0
0x14001cda3  movups  xmm1, xmmword ptr [rax+10h]
0x14001cda7  movups  xmmword ptr [rcx+10h], xmm1
0x14001cdab  movups  xmm0, xmmword ptr [rax+20h]
0x14001cdaf  movups  xmmword ptr [rcx+20h], xmm0
0x14001cdb3  movups  xmm1, xmmword ptr [rax+30h]
0x14001cdb7  movups  xmmword ptr [rcx+30h], xmm1
0x14001cdbb  movups  xmm0, xmmword ptr [rax+40h]
0x14001cdbf  movups  xmmword ptr [rcx+40h], xmm0
0x14001cdc3  movups  xmm1, xmmword ptr [rax+50h]
0x14001cdc7  movups  xmmword ptr [rcx+50h], xmm1
0x14001cdcb  movups  xmm0, xmmword ptr [rax+60h]
0x14001cdcf  movups  xmmword ptr [rcx+60h], xmm0
0x14001cdd3  movups  xmm1, xmmword ptr [rax+70h]
0x14001cdd7  movups  xmmword ptr [rcx+70h], xmm1
0x14001cddb  lea     rcx, [rcx+80h]
0x14001cde2  lea     rax, [rax+80h]
0x14001cde9  sub     rdx, 1
0x14001cded  jnz     short loc_14001CD9D
0x14001cdef  movups  xmm0, xmmword ptr [rax]
0x14001cdf2  movups  xmmword ptr [rcx], xmm0
0x14001cdf5  movups  xmm1, xmmword ptr [rax+10h]
0x14001cdf9  movups  xmmword ptr [rcx+10h], xmm1
0x14001cdfd  movups  xmm0, xmmword ptr [rax+20h]
0x14001ce01  movups  xmmword ptr [rcx+20h], xmm0
0x14001ce05  mov     rax, [rax+30h]
0x14001ce09  mov     [rcx+30h], rax
0x14001ce0d  mov     [rbp+850h+me.dwSize], r12d
0x14001ce14  lea     rdx, [rbp+850h+me]; lpme
0x14001ce1b  mov     rcx, rdi; hSnapshot
0x14001ce1e  call    cs:__imp_Module32NextW
0x14001ce24  test    eax, eax
0x14001ce26  jnz     loc_14001CD03
0x14001ce2c  xor     ebx, ebx
0x14001ce2e  jmp     short loc_14001CE77
0x14001ce30  call    cs:__imp_GetLastError
0x14001ce36  mov     ebx, eax
0x14001ce38  test    eax, eax
0x14001ce3a  jle     short loc_14001CE45
0x14001ce3c  movzx   ebx, ax
0x14001ce3f  or      ebx, 80070000h
0x14001ce45  lea     rax, WPP_GLOBAL_Control
0x14001ce4c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ce53  cmp     rcx, rax
0x14001ce56  jz      short loc_14001CE77
0x14001ce58  test    byte ptr [rcx+1Ch], 1
0x14001ce5c  jz      short loc_14001CE77
0x14001ce5e  mov     edx, 59h ; 'Y'
0x14001ce63  mov     r9d, ebx
0x14001ce66  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001ce6d  mov     rcx, [rcx+10h]
0x14001ce71  call    WPP_SF_d
0x14001ce76  nop
0x14001ce77  cmp     r14, 1
0x14001ce7b  jbe     short loc_14001CE86
0x14001ce7d  mov     rcx, rdi; hObject
0x14001ce80  call    cs:__imp_CloseHandle
0x14001ce86  mov     eax, ebx
0x14001ce88  mov     rcx, [rbp+850h+var_40]
0x14001ce8f  xor     rcx, rsp; StackCookie
0x14001ce92  call    __security_check_cookie
0x14001ce97  add     rsp, 928h
0x14001ce9e  pop     r14
0x14001cea0  pop     r12
0x14001cea2  pop     rdi
0x14001cea3  pop     rsi
0x14001cea4  pop     rbx
0x14001cea5  pop     rbp
0x14001cea6  retn
```
