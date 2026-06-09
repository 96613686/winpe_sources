# AppCompatUtility::UTF16StringFromUTF8String(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,char const *,unsigned __int64)

- ea: `0x180044d84`
- end: `0x180044f1a`
- name: `?UTF16StringFromUTF8String@AppCompatUtility@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD_K@Z`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001325c`

## callees

- `0x18000c190`
- `0x180044d84`
- `0x1800543c0`
- `0x180065150`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180044dbc`
- `KERNEL32!MultiByteToWideChar` at `0x180044e4f`
- `KERNEL32!MultiByteToWideChar` at `0x180044dbc`
- `KERNEL32!MultiByteToWideChar` at `0x180044e4f`
- `KERNEL32!GetLastError` at `0x180044dc9`
- `KERNEL32!GetLastError` at `0x180044e59`
- `KERNEL32!GetLastError` at `0x180044dc9`
- `KERNEL32!GetLastError` at `0x180044e59`
- `ntdll!RtlAllocateHeap` at `0x180044e2a`
- `ntdll!RtlAllocateHeap` at `0x180044e2a`
- `ntdll!RtlFreeHeap` at `0x180044f04`
- `ntdll!RtlFreeHeap` at `0x180044f04`

## string_xrefs

- `0x180044def`: `AppCompatUtility::UTF16StringFromUTF8String`
- `0x180044e7f`: `AppCompatUtility::UTF16StringFromUTF8String`

## pseudocode

```c
__int64 __fastcall AppCompatUtility::UTF16StringFromUTF8String(char **a1, const CHAR *a2, int a3)
{
  int v6; // eax
  int cchWideChar; // r14d
  signed int v8; // eax
  unsigned int v9; // ebx
  _WORD *lpWideCharStr; // rsi
  signed int LastError; // eax
  unsigned __int64 v12; // rdx
  char *v13; // r14
  __int64 v14; // rbx

  v6 = MultiByteToWideChar(0xFDE9u, 0, a2, a3, 0, 0);
  cchWideChar = v6;
  if ( v6 > 0 )
  {
    lpWideCharStr = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (v6 + 1));
    if ( MultiByteToWideChar(0xFDE9u, 0, a2, a3, lpWideCharStr, cchWideChar) > 0 )
    {
      try
      {
        v12 = -1;
        do
          ++v12;
        while ( lpWideCharStr[v12] );
        if ( v12 > (unsigned __int64)a1[3] )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a1);
        }
        else
        {
          if ( (unsigned __int64)a1[3] <= 7 )
            v13 = (char *)a1;
          else
            v13 = *a1;
          a1[2] = (char *)v12;
          v14 = 2 * v12;
          memmove_0(v13, lpWideCharStr, 2 * v12);
          *(_WORD *)&v13[v14] = 0;
        }
      }
      catch ( ... )
      {
        AslLogCallPrintf(1, "AppCompatUtility::UTF16StringFromUTF8String", 1279, "Failed to convert to std::wstring.");
        v9 = -2147467259;
        goto LABEL_17;
      }
      v9 = 0;
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      AslLogCallPrintf(
        1,
        "AppCompatUtility::UTF16StringFromUTF8String",
        1271,
        "Failed to convert UTF8 String to Wstring [0x%x].",
        v9);
    }
LABEL_17:
    if ( lpWideCharStr )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpWideCharStr);
  }
  else
  {
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    AslLogCallPrintf(
      1,
      "AppCompatUtility::UTF16StringFromUTF8String",
      1262,
      "Failed to get buffer size for Wstring [0x%x].",
      v9);
  }
  return v9;
}

```

## disassembly

```asm
0x180044d84  push    rbx
0x180044d86  push    rsi
0x180044d87  push    rdi
0x180044d88  push    r12
0x180044d8a  push    r14
0x180044d8c  push    r15
0x180044d8e  sub     rsp, 48h
0x180044d92  mov     [rsp+78h+var_40], 0FFFFFFFFFFFFFFFEh
0x180044d9b  mov     r15, r8
0x180044d9e  mov     r12, rdx
0x180044da1  mov     rbx, rcx
0x180044da4  xor     edi, edi
0x180044da6  mov     [rsp+78h+cchWideChar], edi; cchWideChar
0x180044daa  mov     [rsp+78h+lpWideCharStr], rdi; lpWideCharStr
0x180044daf  mov     r9d, r8d; cbMultiByte
0x180044db2  mov     r8, rdx; lpMultiByteStr
0x180044db5  xor     edx, edx; dwFlags
0x180044db7  mov     ecx, 0FDE9h; CodePage
0x180044dbc  call    cs:__imp_MultiByteToWideChar
0x180044dc2  mov     r14d, eax
0x180044dc5  test    eax, eax
0x180044dc7  jg      short loc_180044E05
0x180044dc9  call    cs:__imp_GetLastError
0x180044dcf  mov     ebx, eax
0x180044dd1  test    eax, eax
0x180044dd3  jle     short loc_180044DDE
0x180044dd5  movzx   ebx, ax
0x180044dd8  or      ebx, 80070000h
0x180044dde  mov     dword ptr [rsp+78h+lpWideCharStr], ebx
0x180044de2  lea     r9, aFailedToGetBuf; "Failed to get buffer size for Wstring ["...
0x180044de9  mov     r8d, 4EEh
0x180044def  lea     rdx, aAppcompatutili_4; "AppCompatUtility::UTF16StringFromUTF8St"...
0x180044df6  mov     ecx, 1
0x180044dfb  call    AslLogCallPrintf
0x180044e00  jmp     loc_180044F0A
0x180044e05  mov     [rsp+78h+arg_18], 80004005h
0x180044e10  inc     eax
0x180044e12  movsxd  r8, eax
0x180044e15  add     r8, r8; Size
0x180044e18  mov     rcx, gs:60h
0x180044e21  mov     edx, 8; Flags
0x180044e26  mov     rcx, [rcx+30h]; HeapHandle
0x180044e2a  call    cs:__imp_RtlAllocateHeap
0x180044e30  mov     rsi, rax
0x180044e33  mov     [rsp+78h+var_48], rax
0x180044e38  mov     [rsp+78h+cchWideChar], r14d; cchWideChar
0x180044e3d  mov     [rsp+78h+lpWideCharStr], rax; lpWideCharStr
0x180044e42  mov     r9d, r15d; cbMultiByte
0x180044e45  mov     r8, r12; lpMultiByteStr
0x180044e48  xor     edx, edx; dwFlags
0x180044e4a  mov     ecx, 0FDE9h; CodePage
0x180044e4f  call    cs:__imp_MultiByteToWideChar
0x180044e55  test    eax, eax
0x180044e57  jg      short loc_180044E92
0x180044e59  call    cs:__imp_GetLastError
0x180044e5f  mov     ebx, eax
0x180044e61  test    eax, eax
0x180044e63  jle     short loc_180044E6E
0x180044e65  movzx   ebx, ax
0x180044e68  or      ebx, 80070000h
0x180044e6e  mov     dword ptr [rsp+78h+lpWideCharStr], ebx
0x180044e72  lea     r9, aFailedToConver_0; "Failed to convert UTF8 String to Wstrin"...
0x180044e79  mov     r8d, 4F7h
0x180044e7f  lea     rdx, aAppcompatutili_4; "AppCompatUtility::UTF16StringFromUTF8St"...
0x180044e86  mov     ecx, 1
0x180044e8b  call    AslLogCallPrintf
0x180044e90  jmp     short loc_180044EED
0x180044e92  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180044e96  inc     rdx
0x180044e99  cmp     [rsi+rdx*2], di
0x180044e9d  jnz     short loc_180044E96
0x180044e9f  cmp     rdx, [rbx+18h]
0x180044ea3  ja      short loc_180044ED1
0x180044ea5  cmp     qword ptr [rbx+18h], 7
0x180044eaa  jbe     short loc_180044EB1
0x180044eac  mov     r14, [rbx]
0x180044eaf  jmp     short loc_180044EB4
0x180044eb1  mov     r14, rbx
0x180044eb4  mov     [rbx+10h], rdx
0x180044eb8  lea     rbx, [rdx+rdx]
0x180044ebc  mov     r8, rbx; Size
0x180044ebf  mov     rdx, rsi; Src
0x180044ec2  mov     rcx, r14; void *
0x180044ec5  call    memmove_0
0x180044eca  mov     [rbx+r14], di
0x180044ecf  jmp     short loc_180044EDD
0x180044ed1  mov     r9, rsi
0x180044ed4  mov     rcx, rbx
0x180044ed7  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180044edc  nop
0x180044edd  mov     ebx, edi
0x180044edf  jmp     short loc_180044EED
0x180044ee1  mov     ebx, [rsp+78h+arg_18]
0x180044ee8  mov     rsi, [rsp+78h+var_48]
0x180044eed  test    rsi, rsi
0x180044ef0  jz      short loc_180044F0A
0x180044ef2  mov     rcx, gs:60h
0x180044efb  mov     r8, rsi; P
0x180044efe  xor     edx, edx; Flags
0x180044f00  mov     rcx, [rcx+30h]; HeapHandle
0x180044f04  call    cs:__imp_RtlFreeHeap
0x180044f0a  mov     eax, ebx
0x180044f0c  add     rsp, 48h
0x180044f10  pop     r15
0x180044f12  pop     r14
0x180044f14  pop     r12
0x180044f16  pop     rdi
0x180044f17  pop     rsi
0x180044f18  pop     rbx
0x180044f19  retn
```
