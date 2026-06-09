# Apx::ApfIpcIoLinkMgr::OnCmDeviceRemoveCancelled(void)

- ea: `0x180026458`
- end: `0x18002665d`
- name: `?OnCmDeviceRemoveCancelled@ApfIpcIoLinkMgr@Apx@@AEAAXXZ`
- size: `517`
- prototype: `void __fastcall(unsigned __int64 this, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180026ef0`

## callees

- `0x18000a12c`
- `0x18001051c`
- `0x180026458`
- `0x180027068`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026623`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026623`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800264d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800264d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800265d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800265d1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800265bc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800265bc`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLinkMgr::OnCmDeviceRemoveCancelled(unsigned __int64 this, __int64 a2, __int64 a3)
{
  char *v4; // rcx
  __int64 v5; // r8
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  HANDLE FileW; // rax
  __int64 v9; // rdx
  signed int LastError; // eax

  v4 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
      v4 = (char *)WPP_GLOBAL_Control;
    }
    if ( v4 != (char *)&WPP_GLOBAL_Control && v4[28] < 0 && (unsigned __int8)v4[25] >= 4u )
      WPP_SF_q(*((_QWORD *)v4 + 2), 52, a3, ~this);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 16));
  if ( !*(_BYTE *)(this + 117) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, v5, ~this);
    }
    goto LABEL_34;
  }
  *(_BYTE *)(this + 117) = 0;
  if ( *(_QWORD *)(this + 88) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((char *)WPP_GLOBAL_Control + 28) >= 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_34;
    }
    v7 = 54;
    goto LABEL_19;
  }
  if ( !*(_WORD *)(this + 118) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((char *)WPP_GLOBAL_Control + 28) >= 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_34;
    }
    v7 = 55;
LABEL_19:
    WPP_SF_qd(v6[2], v7, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids, ~this, 0);
    goto LABEL_34;
  }
  FileW = CreateFileW((LPCWSTR)(this + 118), 0xC0000000, 3u, 0, 3u, 0x40800000u, 0);
  *(_QWORD *)(this + 88) = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    LOBYTE(v9) = 1;
    (*(void (__fastcall **)(_QWORD, __int64))(this + 56))(*(_QWORD *)(this + 64), v9);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    *(_QWORD *)(this + 88) = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids,
        ~this,
        LastError);
    }
  }
LABEL_34:
  LeaveCriticalSection((LPCRITICAL_SECTION)(this + 16));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  }
}

```

## disassembly

```asm
0x180026458  push    rbx
0x18002645a  push    rbp
0x18002645b  push    rsi
0x18002645c  push    rdi
0x18002645d  push    r15
0x18002645f  sub     rsp, 40h
0x180026463  mov     rbx, rcx
0x180026466  mov     rcx, cs:WPP_GLOBAL_Control
0x18002646d  lea     rbp, WPP_GLOBAL_Control
0x180026474  lea     r15, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x18002647b  cmp     rcx, rbp
0x18002647e  jz      short loc_1800264C9
0x180026480  test    byte ptr [rcx+1Ch], 1
0x180026484  jz      short loc_1800264A4
0x180026486  cmp     byte ptr [rcx+19h], 5
0x18002648a  jb      short loc_1800264A4
0x18002648c  mov     rcx, [rcx+10h]
0x180026490  mov     edx, 33h ; '3'
0x180026495  mov     r8, r15
0x180026498  call    WPP_SF_
0x18002649d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800264a4  cmp     rcx, rbp
0x1800264a7  jz      short loc_1800264C9
0x1800264a9  test    byte ptr [rcx+1Ch], 80h
0x1800264ad  jz      short loc_1800264C9
0x1800264af  cmp     byte ptr [rcx+19h], 4
0x1800264b3  jb      short loc_1800264C9
0x1800264b5  mov     rcx, [rcx+10h]
0x1800264b9  mov     r9, rbx
0x1800264bc  not     r9
0x1800264bf  mov     edx, 34h ; '4'
0x1800264c4  call    WPP_SF_q
0x1800264c9  lea     rdi, [rbx+10h]
0x1800264cd  mov     rcx, rdi; lpCriticalSection
0x1800264d0  call    cs:__imp_EnterCriticalSection
0x1800264d6  xor     esi, esi
0x1800264d8  cmp     [rbx+75h], sil
0x1800264dc  jnz     short loc_180026519
0x1800264de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800264e5  cmp     rcx, rbp
0x1800264e8  jz      loc_180026620
0x1800264ee  test    byte ptr [rcx+1Ch], 80h
0x1800264f2  jz      loc_180026620
0x1800264f8  cmp     byte ptr [rcx+19h], 3
0x1800264fc  jb      loc_180026620
0x180026502  mov     rcx, [rcx+10h]
0x180026506  lea     edx, [rsi+35h]
0x180026509  not     rbx
0x18002650c  mov     r9, rbx
0x18002650f  call    WPP_SF_q
0x180026514  jmp     loc_180026620
0x180026519  mov     [rbx+75h], sil
0x18002651d  cmp     [rbx+58h], rsi
0x180026521  jz      short loc_180026567
0x180026523  mov     rcx, cs:WPP_GLOBAL_Control
0x18002652a  cmp     rcx, rbp
0x18002652d  jz      loc_180026620
0x180026533  test    byte ptr [rcx+1Ch], 80h
0x180026537  jz      loc_180026620
0x18002653d  cmp     byte ptr [rcx+19h], 3
0x180026541  jb      loc_180026620
0x180026547  mov     edx, 36h ; '6'
0x18002654c  mov     [rsp+68h+dwCreationDisposition], esi
0x180026550  mov     rcx, [rcx+10h]
0x180026554  not     rbx
0x180026557  mov     r9, rbx
0x18002655a  mov     r8, r15
0x18002655d  call    WPP_SF_qd
0x180026562  jmp     loc_180026620
0x180026567  lea     rcx, [rbx+76h]; lpFileName
0x18002656b  cmp     [rcx], si
0x18002656e  jnz     short loc_18002659B
0x180026570  mov     rcx, cs:WPP_GLOBAL_Control
0x180026577  cmp     rcx, rbp
0x18002657a  jz      loc_180026620
0x180026580  test    byte ptr [rcx+1Ch], 80h
0x180026584  jz      loc_180026620
0x18002658a  cmp     byte ptr [rcx+19h], 3
0x18002658e  jb      loc_180026620
0x180026594  mov     edx, 37h ; '7'
0x180026599  jmp     short loc_18002654C
0x18002659b  xor     r9d, r9d; lpSecurityAttributes
0x18002659e  mov     [rsp+68h+hTemplateFile], rsi; hTemplateFile
0x1800265a3  mov     [rsp+68h+dwFlagsAndAttributes], 40800000h; dwFlagsAndAttributes
0x1800265ab  mov     edx, 0C0000000h; dwDesiredAccess
0x1800265b0  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800265b8  lea     r8d, [r9+3]; dwShareMode
0x1800265bc  call    cs:__imp_CreateFileW
0x1800265c2  mov     [rbx+58h], rax
0x1800265c6  inc     rax
0x1800265c9  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800265cf  jnz     short loc_18002660D
0x1800265d1  call    cs:__imp_GetLastError
0x1800265d7  test    eax, eax
0x1800265d9  jle     short loc_1800265E3
0x1800265db  movzx   eax, ax
0x1800265de  or      eax, 80070000h
0x1800265e3  mov     [rbx+58h], rsi
0x1800265e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800265ee  cmp     rcx, rbp
0x1800265f1  jz      short loc_180026620
0x1800265f3  test    byte ptr [rcx+1Ch], 80h
0x1800265f7  jz      short loc_180026620
0x1800265f9  cmp     byte ptr [rcx+19h], 2
0x1800265fd  jb      short loc_180026620
0x1800265ff  mov     edx, 38h ; '8'
0x180026604  mov     [rsp+68h+dwCreationDisposition], eax
0x180026608  jmp     loc_180026550
0x18002660d  mov     rcx, [rbx+40h]
0x180026611  mov     r8b, 1
0x180026614  mov     rax, [rbx+38h]
0x180026618  mov     dl, r8b
0x18002661b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026620  mov     rcx, rdi; lpCriticalSection
0x180026623  call    cs:__imp_LeaveCriticalSection
0x180026629  mov     rcx, cs:WPP_GLOBAL_Control
0x180026630  cmp     rcx, rbp
0x180026633  jz      short loc_180026652
0x180026635  test    byte ptr [rcx+1Ch], 1
0x180026639  jz      short loc_180026652
0x18002663b  cmp     byte ptr [rcx+19h], 5
0x18002663f  jb      short loc_180026652
0x180026641  mov     rcx, [rcx+10h]
0x180026645  mov     edx, 39h ; '9'
0x18002664a  mov     r8, r15
0x18002664d  call    WPP_SF_
0x180026652  add     rsp, 40h
0x180026656  pop     r15
0x180026658  pop     rdi
0x180026659  pop     rsi
0x18002665a  pop     rbp
0x18002665b  pop     rbx
0x18002665c  retn
```
