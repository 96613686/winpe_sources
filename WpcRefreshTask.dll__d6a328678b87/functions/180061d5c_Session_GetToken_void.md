# Session::GetToken(void)

- ea: `0x180061d5c`
- end: `0x180061e9e`
- name: `?GetToken@Session@@QEBA?AVToken@@XZ`
- size: `322`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18002aae4`
- `0x180092c78`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x180035e0c`
- `0x180046660`
- `0x18006105c`
- `0x180061d5c`
- `0x180063658`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061e37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061e37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061e0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061e0f`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180061da2`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180061da2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Session::GetToken(unsigned int *a1, _QWORD *a2)
{
  __int64 v4; // rax
  int UserToken; // edi
  _BYTE *v6; // rdx
  signed int LastError; // eax
  unsigned int v9; // ebx
  HANDLE hObject; // [rsp+30h] [rbp-59h] BYREF
  _QWORD *v11; // [rsp+38h] [rbp-51h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+48h] [rbp-41h] BYREF
  _QWORD *v13; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v14[56]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE *v15; // [rsp+B0h] [rbp+27h]

  v11 = a2;
  hObject = 0;
  v4 = stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(&v13, &hObject);
  UserToken = QueryUserToken(*a1, v4);
  if ( v15 )
  {
    v11 = v13;
    (*(void (__fastcall **)(_BYTE *, _QWORD **))(*(_QWORD *)v15 + 16LL))(v15, &v11);
    if ( v15 )
    {
      v6 = v14;
      LOBYTE(v6) = v15 != v14;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v15 + 32LL))(v15, v6);
    }
  }
  if ( !UserToken )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_dd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_f3234619ce433b755bc88a9d02f62b22_Traceguids, *a1, v9);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v9);
    throw (ErrorCodeException *)pExceptionObject;
  }
  Token::Token(a2, (__int64 *)&hObject);
  if ( hObject && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return a2;
}

```

## disassembly

```asm
0x180061d5c  mov     [rsp-8+arg_10], rbx
0x180061d61  push    rbp
0x180061d62  push    rsi
0x180061d63  push    rdi
0x180061d64  lea     rbp, [rsp-47h]
0x180061d69  sub     rsp, 0D0h
0x180061d70  mov     rax, cs:__security_cookie
0x180061d77  xor     rax, rsp
0x180061d7a  mov     [rbp+57h+var_20], rax
0x180061d7e  mov     rbx, rdx
0x180061d81  mov     rsi, rcx
0x180061d84  mov     [rbp+57h+var_A8], rdx
0x180061d88  mov     [rbp+57h+hObject], 0
0x180061d90  lea     rdx, [rbp+57h+hObject]
0x180061d94  lea     rcx, [rbp+57h+var_70]
0x180061d98  call    ??$get_pointer@V?$unique_ptr@XUHandleClose@Private@@@std@@@stdext@@YA?AV?$GetPointer@PEAX@0@AEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(std::unique_ptr<void,Private::HandleClose> &)
0x180061d9d  mov     rdx, rax
0x180061da0  mov     ecx, [rsi]
0x180061da2  call    cs:__imp_QueryUserToken
0x180061da8  mov     edi, eax
0x180061daa  mov     rcx, [rbp+57h+var_30]
0x180061dae  test    rcx, rcx
0x180061db1  jz      short loc_180061DEB
0x180061db3  mov     rdx, [rbp+57h+var_70]
0x180061db7  mov     [rbp+57h+var_A8], rdx
0x180061dbb  mov     rdx, [rcx]
0x180061dbe  mov     rax, [rdx+10h]
0x180061dc2  lea     rdx, [rbp+57h+var_A8]
0x180061dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061dcb  mov     rcx, [rbp+57h+var_30]
0x180061dcf  test    rcx, rcx
0x180061dd2  jz      short loc_180061DEB
0x180061dd4  mov     rax, [rcx]
0x180061dd7  lea     rdx, [rbp+57h+var_68]
0x180061ddb  cmp     rcx, rdx
0x180061dde  setnz   dl
0x180061de1  mov     rax, [rax+20h]
0x180061de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061dea  nop
0x180061deb  test    edi, edi
0x180061ded  jz      short loc_180061E37
0x180061def  lea     rdx, [rbp+57h+hObject]
0x180061df3  mov     rcx, rbx
0x180061df6  call    ??0Token@@QEAA@$$QEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; Token::Token(std::unique_ptr<void,Private::HandleClose> &&)
0x180061dfb  nop
0x180061dfc  mov     rcx, [rbp+57h+hObject]; hObject
0x180061e00  test    rcx, rcx
0x180061e03  jz      short loc_180061E15
0x180061e05  lea     rdx, [rcx-1]
0x180061e09  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180061e0d  ja      short loc_180061E15
0x180061e0f  call    cs:__imp_CloseHandle
0x180061e15  mov     rax, rbx
0x180061e18  mov     rcx, [rbp+57h+var_20]
0x180061e1c  xor     rcx, rsp; StackCookie
0x180061e1f  call    __security_check_cookie
0x180061e24  mov     rbx, [rsp+0E0h+arg_10]
0x180061e2c  add     rsp, 0D0h
0x180061e33  pop     rdi
0x180061e34  pop     rsi
0x180061e35  pop     rbp
0x180061e36  retn
0x180061e37  call    cs:__imp_GetLastError
0x180061e3d  nop
0x180061e3e  mov     ebx, eax
0x180061e40  test    eax, eax
0x180061e42  jle     short loc_180061E4D
0x180061e44  movzx   ebx, ax
0x180061e47  or      ebx, 80070000h
0x180061e4d  lea     rax, WPP_GLOBAL_Control
0x180061e54  mov     rcx, cs:WPP_GLOBAL_Control
0x180061e5b  cmp     rcx, rax
0x180061e5e  jz      short loc_180061E82
0x180061e60  test    byte ptr [rcx+1Ch], 1
0x180061e64  jz      short loc_180061E82
0x180061e66  mov     edx, 0Fh
0x180061e6b  mov     [rsp+0E0h+var_C0], ebx
0x180061e6f  mov     r9d, [rsi]
0x180061e72  lea     r8, WPP_f3234619ce433b755bc88a9d02f62b22_Traceguids
0x180061e79  mov     rcx, [rcx+10h]
0x180061e7d  call    WPP_SF_dd
0x180061e82  mov     edx, ebx; int
0x180061e84  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180061e88  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180061e8d  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180061e94  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180061e98  call    _CxxThrowException_0
```
