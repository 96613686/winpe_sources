# UpdateSessionLogger::OpenEtlFileProtectionHandle(void)

- ea: `0x1400956e0`
- end: `0x140095818`
- name: `?OpenEtlFileProtectionHandle@UpdateSessionLogger@@AEAAJXZ`
- size: `312`
- prototype: `__int64 __fastcall(UpdateSessionLogger *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x140095bd0`

## callees

- `0x140085d38`
- `0x140085d94`
- `0x1400950b0`
- `0x1400956e0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140095733`
- `KERNEL32!CreateFileW` at `0x140095733`
- `KERNEL32!Sleep` at `0x140095760`
- `KERNEL32!Sleep` at `0x140095760`
- `KERNEL32!GetLastError` at `0x14009574b`
- `KERNEL32!GetLastError` at `0x14009574b`

## pseudocode

```c
__int64 __fastcall UpdateSessionLogger::OpenEtlFileProtectionHandle(UpdateSessionLogger *this)
{
  int v2; // esi
  const WCHAR **v3; // rbx
  const WCHAR *v4; // rcx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  int v7; // edi

  UpdateSessionLogger::CloseEtlFileProtectionHandle(this);
  v2 = 0;
  v3 = (const WCHAR **)((char *)this + 88);
  while ( 1 )
  {
    v4 = (const WCHAR *)((char *)this + 88);
    if ( *((_QWORD *)this + 14) > 7u )
      v4 = *v3;
    FileW = CreateFileW(v4, 1u, 3u, 0, 3u, 0x80u, 0);
    *((_QWORD *)this + 161) = FileW;
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      break;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError != 2 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        if ( *((_QWORD *)this + 14) > 7u )
          v3 = (const WCHAR **)*v3;
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          65,
          (unsigned int)&WPP_59ae06a751773575a42227eddeae96fd_Traceguids,
          (_DWORD)v3,
          LastError);
      }
      if ( v7 > 0 )
        return (unsigned __int16)v7 | 0x80070000;
      return (unsigned int)v7;
    }
    Sleep(0x64u);
    if ( ++v2 >= 2 )
      return 2147942402LL;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    if ( *((_QWORD *)this + 14) > 7u )
      v3 = (const WCHAR **)*v3;
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 64, &WPP_59ae06a751773575a42227eddeae96fd_Traceguids, v3);
  }
  return 0;
}

```

## disassembly

```asm
0x1400956e0  mov     [rsp+arg_0], rbx
0x1400956e5  mov     [rsp+arg_8], rbp
0x1400956ea  mov     [rsp+arg_10], rsi
0x1400956ef  push    rdi
0x1400956f0  sub     rsp, 40h
0x1400956f4  mov     rbp, rcx
0x1400956f7  call    ?CloseEtlFileProtectionHandle@UpdateSessionLogger@@AEAAXXZ; UpdateSessionLogger::CloseEtlFileProtectionHandle(void)
0x1400956fc  xor     esi, esi
0x1400956fe  lea     rbx, [rbp+58h]
0x140095702  cmp     qword ptr [rbp+70h], 7
0x140095707  mov     rcx, rbx
0x14009570a  jbe     short loc_14009570F
0x14009570c  mov     rcx, [rbx]; lpFileName
0x14009570f  xor     r9d, r9d; lpSecurityAttributes
0x140095712  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x14009571b  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140095723  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x14009572b  lea     edx, [r9+1]; dwDesiredAccess
0x14009572f  lea     r8d, [r9+3]; dwShareMode
0x140095733  call    cs:__imp_CreateFileW
0x140095739  mov     [rbp+508h], rax
0x140095740  inc     rax
0x140095743  test    rax, 0FFFFFFFFFFFFFFFEh
0x140095749  jnz     short loc_1400957C6
0x14009574b  call    cs:__imp_GetLastError
0x140095751  mov     edi, eax
0x140095753  cmp     eax, 2
0x140095756  jnz     short loc_140095776
0x140095758  cmp     esi, 4
0x14009575b  jge     short loc_140095776
0x14009575d  lea     ecx, [rax+62h]; dwMilliseconds
0x140095760  call    cs:__imp_Sleep
0x140095766  inc     esi
0x140095768  cmp     esi, edi
0x14009576a  jl      short loc_140095702
0x14009576c  mov     eax, 80070002h
0x140095771  jmp     loc_140095803
0x140095776  mov     rcx, cs:WPP_GLOBAL_Control
0x14009577d  lea     rax, WPP_GLOBAL_Control
0x140095784  cmp     rcx, rax
0x140095787  jz      short loc_1400957B5
0x140095789  test    byte ptr [rcx+1Ch], 2
0x14009578d  jz      short loc_1400957B5
0x14009578f  cmp     qword ptr [rbx+18h], 7
0x140095794  jbe     short loc_140095799
0x140095796  mov     rbx, [rbx]
0x140095799  mov     rcx, [rcx+10h]
0x14009579d  lea     r8, WPP_59ae06a751773575a42227eddeae96fd_Traceguids
0x1400957a4  mov     edx, 41h ; 'A'
0x1400957a9  mov     [rsp+48h+dwCreationDisposition], edi
0x1400957ad  mov     r9, rbx
0x1400957b0  call    WPP_SF_Sd
0x1400957b5  test    edi, edi
0x1400957b7  jle     short loc_1400957C2
0x1400957b9  movzx   edi, di
0x1400957bc  or      edi, 80070000h
0x1400957c2  mov     eax, edi
0x1400957c4  jmp     short loc_140095803
0x1400957c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400957cd  lea     rax, WPP_GLOBAL_Control
0x1400957d4  cmp     rcx, rax
0x1400957d7  jz      short loc_140095801
0x1400957d9  test    byte ptr [rcx+1Ch], 4
0x1400957dd  jz      short loc_140095801
0x1400957df  cmp     qword ptr [rbx+18h], 7
0x1400957e4  jbe     short loc_1400957E9
0x1400957e6  mov     rbx, [rbx]
0x1400957e9  mov     rcx, [rcx+10h]
0x1400957ed  lea     r8, WPP_59ae06a751773575a42227eddeae96fd_Traceguids
0x1400957f4  mov     edx, 40h ; '@'
0x1400957f9  mov     r9, rbx
0x1400957fc  call    WPP_SF_S
0x140095801  xor     eax, eax
0x140095803  mov     rbx, [rsp+48h+arg_0]
0x140095808  mov     rbp, [rsp+48h+arg_8]
0x14009580d  mov     rsi, [rsp+48h+arg_10]
0x140095812  add     rsp, 40h
0x140095816  pop     rdi
0x140095817  retn
```
