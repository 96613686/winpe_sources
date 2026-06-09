# EvtClearLog

- ea: `0x180025f90`
- end: `0x18002613c`
- name: `EvtClearLog`
- size: `428`
- prototype: `BOOL __stdcall(EVT_HANDLE Session, LPCWSTR ChannelPath, LPCWSTR TargetFilePath, DWORD Flags)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800267dc`

## callees

- `0x180006aec`
- `0x180007940`
- `0x180007aa0`
- `0x18000a724`
- `0x18000c404`
- `0x180013f6c`
- `0x180014bb0`
- `0x180023548`
- `0x180025f90`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026116`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026116`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __stdcall EvtClearLog(EVT_HANDLE Session, LPCWSTR ChannelPath, LPCWSTR TargetFilePath, DWORD Flags)
{
  BOOL v7; // ebx
  const wchar_t *v8; // rdi
  DWORD v9; // edi
  struct Session *v11; // [rsp+20h] [rbp-98h] BYREF
  __int128 pExceptionObject; // [rsp+28h] [rbp-90h] BYREF
  __int64 v13; // [rsp+38h] [rbp-80h]
  int v14; // [rsp+40h] [rbp-78h]
  int v15; // [rsp+44h] [rbp-74h]
  int v16; // [rsp+48h] [rbp-70h]
  __int128 v17; // [rsp+50h] [rbp-68h] BYREF
  __int64 v18; // [rsp+60h] [rbp-58h]
  int v19; // [rsp+68h] [rbp-50h]
  int v20; // [rsp+6Ch] [rbp-4Ch]
  int v21; // [rsp+70h] [rbp-48h]
  EvtException *v22; // [rsp+78h] [rbp-40h] BYREF
  wchar_t *v23[4]; // [rsp+80h] [rbp-38h] BYREF

  LastErrInfo::Reset((LastErrInfo *)Session);
  try
  {
    v7 = 0;
    if ( Flags )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      pExceptionObject = 0;
      v13 = 0;
      v14 = 87;
      v15 = -1;
      v16 = 1157;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !ChannelPath )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      v17 = 0;
      v18 = 0;
      v19 = 87;
      v20 = -1;
      v21 = 1162;
      throw (EvtException *)&v17;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v23);
    if ( TargetFilePath )
    {
      FullyQualifyFilePath((__int64)v23, TargetFilePath);
      v8 = v23[0];
    }
    else
    {
      v8 = 0;
    }
    GetSession(&v11);
    LogHandle::ClearLog(v11, ChannelPath, v8, 0);
    v9 = 0;
    wmi::AutoRef<Object>::Release(&v11);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v23);
  }
  catch ( EvtException *v22 )
  {
    v7 = 0;
    v9 = *((_DWORD *)v22 + 6);
  }
  SetLastError(v9);
  LOBYTE(v7) = v9 == 0;
  return v7;
}

```

## disassembly

```asm
0x180025f90  mov     [rsp+arg_0], rbx
0x180025f95  mov     [rsp+arg_8], rsi
0x180025f9a  push    rdi
0x180025f9b  push    r14
0x180025f9d  push    r15
0x180025f9f  sub     rsp, 0A0h
0x180025fa6  mov     r14d, r9d
0x180025fa9  mov     rdi, r8
0x180025fac  mov     rsi, rdx
0x180025faf  mov     r15, rcx
0x180025fb2  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x180025fb7  xor     ebx, ebx
0x180025fb9  test    r14d, r14d
0x180025fbc  jz      short loc_18002602B
0x180025fbe  lea     rax, WPP_GLOBAL_Control
0x180025fc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180025fcc  cmp     rcx, rax
0x180025fcf  jz      short loc_180025FF4
0x180025fd1  test    byte ptr [rcx+1Ch], 1
0x180025fd5  jz      short loc_180025FF4
0x180025fd7  cmp     byte ptr [rcx+19h], 2
0x180025fdb  jb      short loc_180025FF4
0x180025fdd  lea     edx, [rbx+22h]
0x180025fe0  lea     r9d, [rbx+57h]
0x180025fe4  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x180025feb  mov     rcx, [rcx+10h]
0x180025fef  call    WPP_SF_D
0x180025ff4  xorps   xmm0, xmm0
0x180025ff7  movdqu  [rsp+0B8h+pExceptionObject], xmm0
0x180025ffd  mov     [rsp+0B8h+var_80], rbx
0x180026002  mov     [rsp+0B8h+var_78], 57h ; 'W'
0x18002600a  mov     [rsp+0B8h+var_74], 0FFFFFFFFh
0x180026012  mov     [rsp+0B8h+var_70], 485h
0x18002601a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026021  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x180026026  call    _CxxThrowException_0
0x18002602b  test    rsi, rsi
0x18002602e  jnz     short loc_18002609D
0x180026030  lea     rax, WPP_GLOBAL_Control
0x180026037  mov     rcx, cs:WPP_GLOBAL_Control
0x18002603e  cmp     rcx, rax
0x180026041  jz      short loc_180026066
0x180026043  test    byte ptr [rcx+1Ch], 1
0x180026047  jz      short loc_180026066
0x180026049  cmp     byte ptr [rcx+19h], 2
0x18002604d  jb      short loc_180026066
0x18002604f  lea     edx, [rsi+23h]
0x180026052  lea     r9d, [rsi+57h]
0x180026056  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18002605d  mov     rcx, [rcx+10h]
0x180026061  call    WPP_SF_D
0x180026066  xorps   xmm0, xmm0
0x180026069  movdqu  [rsp+0B8h+var_68], xmm0
0x18002606f  mov     [rsp+0B8h+var_58], rbx
0x180026074  mov     [rsp+0B8h+var_50], 57h ; 'W'
0x18002607c  mov     [rsp+0B8h+var_4C], 0FFFFFFFFh
0x180026084  mov     [rsp+0B8h+var_48], 48Ah
0x18002608c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026093  lea     rcx, [rsp+0B8h+var_68]; pExceptionObject
0x180026098  call    _CxxThrowException_0
0x18002609d  lea     rcx, [rsp+0B8h+var_38]
0x1800260a5  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800260aa  nop
0x1800260ab  test    rdi, rdi
0x1800260ae  jz      short loc_1800260CA
0x1800260b0  mov     rdx, rdi
0x1800260b3  lea     rcx, [rsp+0B8h+var_38]
0x1800260bb  call    FullyQualifyFilePath
0x1800260c0  mov     rdi, [rsp+0B8h+var_38]
0x1800260c8  jmp     short loc_1800260CD
0x1800260ca  mov     rdi, rbx
0x1800260cd  mov     rdx, r15
0x1800260d0  lea     rcx, [rsp+0B8h+var_98]; void *
0x1800260d5  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x1800260da  nop
0x1800260db  xor     r9d, r9d; unsigned int
0x1800260de  mov     r8, rdi; wchar_t *
0x1800260e1  mov     rdx, rsi; wchar_t *
0x1800260e4  mov     rcx, [rsp+0B8h+var_98]; this
0x1800260e9  call    ?ClearLog@LogHandle@@SAXPEAVSession@@PEB_W1K@Z; LogHandle::ClearLog(Session *,wchar_t const *,wchar_t const *,ulong)
0x1800260ee  mov     edi, ebx
0x1800260f0  lea     rcx, [rsp+0B8h+var_98]; void *
0x1800260f5  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x1800260fa  nop
0x1800260fb  lea     rcx, [rsp+0B8h+var_38]
0x180026103  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180026108  nop
0x180026109  jmp     short loc_180026114
0x18002610b  xor     ebx, ebx
0x18002610d  mov     edi, [rsp+0B8h+arg_18]
0x180026114  mov     ecx, edi; dwErrCode
0x180026116  call    cs:__imp_SetLastError
0x18002611c  test    edi, edi
0x18002611e  setz    bl
0x180026121  mov     eax, ebx
0x180026123  lea     r11, [rsp+0B8h+var_18]
0x18002612b  mov     rbx, [r11+20h]
0x18002612f  mov     rsi, [r11+28h]
0x180026133  mov     rsp, r11
0x180026136  pop     r15
0x180026138  pop     r14
0x18002613a  pop     rdi
0x18002613b  retn
```
