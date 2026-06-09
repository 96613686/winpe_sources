# IsDeleteBrowserHistoryActivation(ushort const *,IInspectable *)

- ea: `0x180053b78`
- end: `0x180053c63`
- name: `?IsDeleteBrowserHistoryActivation@@YA_NPEBGPEAUIInspectable@@@Z`
- size: `235`
- prototype: `bool __fastcall(const unsigned __int16 *, struct IInspectable *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003bf90`

## callees

- `0x180053b78`
- `0x180086060`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180053b9a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180053c19`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180053c2e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180053b9a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180053c19`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180053c2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053bb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053c4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053bb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053c4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053be7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053be7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053c42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053c42`
- `api-ms-win-core-commandlinetoargv-l1-1-0!CommandLineToArgvW` at `0x180053bf5`
- `api-ms-win-core-commandlinetoargv-l1-1-0!CommandLineToArgvW` at `0x180053bf5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall IsDeleteBrowserHistoryActivation(const unsigned __int16 *a1, struct IInspectable *a2)
{
  char v3; // si
  HSTRING v4; // rcx
  const WCHAR *StringRawBuffer; // rax
  LPWSTR *v6; // rdi
  int i; // ebx
  int pNumArgs; // [rsp+48h] [rbp+10h] BYREF
  HSTRING string; // [rsp+50h] [rbp+18h] BYREF

  v3 = 0;
  if ( a2 && !(unsigned int)_o__wcsicmp(a1, L"Windows.Launch") )
  {
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    if ( (int)GetCommandsForWindowsLaunchContract(a2, &string) >= 0 )
    {
      v4 = string;
      if ( !string )
      {
LABEL_14:
        WindowsDeleteString(v4);
        return v3;
      }
      pNumArgs = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v6 = CommandLineToArgvW(StringRawBuffer, &pNumArgs);
      if ( v6 )
      {
        for ( i = 0; i < pNumArgs; ++i )
        {
          if ( !(unsigned int)_o__wcsicmp(v6[i], L"-dbh") || !(unsigned int)_o__wcsicmp(v6[i], L"/dbh") )
          {
            v3 = 1;
            break;
          }
        }
        LocalFree(v6);
      }
    }
    v4 = string;
    goto LABEL_14;
  }
  return v3;
}

```

## disassembly

```asm
0x180053b78  mov     [rsp+arg_0], rbx
0x180053b7d  push    rbp
0x180053b7e  push    rsi
0x180053b7f  push    rdi
0x180053b80  sub     rsp, 20h
0x180053b84  mov     rbx, rdx
0x180053b87  xor     sil, sil
0x180053b8a  test    rdx, rdx
0x180053b8d  jz      loc_180053C53
0x180053b93  lea     rdx, String2; "Windows.Launch"
0x180053b9a  call    cs:__imp__o__wcsicmp
0x180053ba0  test    eax, eax
0x180053ba2  jnz     loc_180053C53
0x180053ba8  mov     [rsp+38h+string], 0
0x180053bb1  xor     ecx, ecx; string
0x180053bb3  call    cs:__imp_WindowsDeleteString
0x180053bb9  mov     [rsp+38h+string], 0
0x180053bc2  lea     rdx, [rsp+38h+string]
0x180053bc7  mov     rcx, rbx
0x180053bca  call    GetCommandsForWindowsLaunchContract
0x180053bcf  test    eax, eax
0x180053bd1  js      short loc_180053C48
0x180053bd3  mov     rcx, [rsp+38h+string]; string
0x180053bd8  test    rcx, rcx
0x180053bdb  jz      short loc_180053C4D
0x180053bdd  mov     [rsp+38h+pNumArgs], 0
0x180053be5  xor     edx, edx; length
0x180053be7  call    cs:__imp_WindowsGetStringRawBuffer
0x180053bed  lea     rdx, [rsp+38h+pNumArgs]; pNumArgs
0x180053bf2  mov     rcx, rax; lpCmdLine
0x180053bf5  call    cs:__imp_CommandLineToArgvW
0x180053bfb  mov     rdi, rax
0x180053bfe  test    rax, rax
0x180053c01  jz      short loc_180053C48
0x180053c03  xor     ebx, ebx
0x180053c05  cmp     ebx, [rsp+38h+pNumArgs]
0x180053c09  jge     short loc_180053C3F
0x180053c0b  movsxd  rbp, ebx
0x180053c0e  lea     rdx, aDbh; "-dbh"
0x180053c15  mov     rcx, [rdi+rbp*8]
0x180053c19  call    cs:__imp__o__wcsicmp
0x180053c1f  test    eax, eax
0x180053c21  jz      short loc_180053C3C
0x180053c23  lea     rdx, aDbh_0; "/dbh"
0x180053c2a  mov     rcx, [rdi+rbp*8]
0x180053c2e  call    cs:__imp__o__wcsicmp
0x180053c34  test    eax, eax
0x180053c36  jz      short loc_180053C3C
0x180053c38  inc     ebx
0x180053c3a  jmp     short loc_180053C05
0x180053c3c  mov     sil, 1
0x180053c3f  mov     rcx, rdi; hMem
0x180053c42  call    cs:__imp_LocalFree
0x180053c48  mov     rcx, [rsp+38h+string]; string
0x180053c4d  call    cs:__imp_WindowsDeleteString
0x180053c53  mov     al, sil
0x180053c56  mov     rbx, [rsp+38h+arg_0]
0x180053c5b  add     rsp, 20h
0x180053c5f  pop     rdi
0x180053c60  pop     rsi
0x180053c61  pop     rbp
0x180053c62  retn
```
