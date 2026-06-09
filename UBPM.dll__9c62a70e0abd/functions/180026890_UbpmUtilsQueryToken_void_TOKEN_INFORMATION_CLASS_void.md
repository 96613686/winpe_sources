# UbpmUtilsQueryToken(void *,_TOKEN_INFORMATION_CLASS,void * *)

- ea: `0x180026890`
- end: `0x180026a69`
- name: `?UbpmUtilsQueryToken@@YAKPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z`
- size: `473`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, TOKEN_INFORMATION_CLASS TokenInformationClass, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001eaf4`

## callees

- `0x180026890`
- `0x1800351ec`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800268bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002692b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800268bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002692b`
- `ntdll!RtlFreeHeap` at `0x180026a56`
- `ntdll!RtlFreeHeap` at `0x180026a56`
- `ntdll!RtlAllocateHeap` at `0x1800268fc`
- `ntdll!RtlAllocateHeap` at `0x1800268fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800269b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800269b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800269ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800269ab`

## pseudocode

```c
DWORD __fastcall UbpmUtilsQueryToken(HANDLE TokenHandle, TOKEN_INFORMATION_CLASS TokenInformationClass, void **a3)
{
  PVOID Heap; // rbx
  DWORD result; // eax
  unsigned int v8; // ebx
  DWORD LastError; // eax
  DWORD v10; // edi
  DWORD TokenInformationLength; // [rsp+58h] [rbp+20h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenInformationClass, 0, 0, &TokenInformationLength) || GetLastError() == 122 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, TokenInformationLength);
    if ( Heap )
    {
      if ( GetTokenInformation(
             TokenHandle,
             TokenInformationClass,
             Heap,
             TokenInformationLength,
             &TokenInformationLength) )
      {
        result = 0;
        *a3 = Heap;
      }
      else
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, LastError);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        return v10;
      }
    }
    else
    {
      SetLastError(8u);
      result = GetLastError();
      v8 = result;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, result);
        return v8;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, 13);
    return 13;
  }
  return result;
}

```

## disassembly

```asm
0x180026890  mov     [rsp+arg_8], rbp
0x180026895  mov     [rsp+arg_10], rsi
0x18002689a  push    rdi
0x18002689b  sub     rsp, 30h
0x18002689f  mov     rdi, r8
0x1800268a2  mov     [rsp+38h+TokenInformationLength], 0
0x1800268aa  lea     rax, [rsp+38h+TokenInformationLength]
0x1800268af  xor     r8d, r8d; TokenInformation
0x1800268b2  xor     r9d, r9d; TokenInformationLength
0x1800268b5  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800268ba  mov     esi, edx
0x1800268bc  mov     rbp, rcx
0x1800268bf  call    cs:__imp_GetTokenInformation
0x1800268c6  nop     dword ptr [rax+rax+00h]
0x1800268cb  test    eax, eax
0x1800268cd  jnz     short loc_1800268E0
0x1800268cf  call    cs:__imp_GetLastError
0x1800268d6  nop     dword ptr [rax+rax+00h]
0x1800268db  cmp     eax, 7Ah ; 'z'
0x1800268de  jnz     short loc_18002695A
0x1800268e0  mov     rcx, gs:60h
0x1800268e9  mov     edx, 8; Flags
0x1800268ee  mov     r8d, [rsp+38h+TokenInformationLength]; Size
0x1800268f3  mov     [rsp+38h+arg_0], rbx
0x1800268f8  mov     rcx, [rcx+30h]; HeapHandle
0x1800268fc  call    cs:__imp_RtlAllocateHeap
0x180026903  nop     dword ptr [rax+rax+00h]
0x180026908  mov     rbx, rax
0x18002690b  test    rax, rax
0x18002690e  jz      loc_1800269A6
0x180026914  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180026919  lea     rax, [rsp+38h+TokenInformationLength]
0x18002691e  mov     r8, rbx; TokenInformation
0x180026921  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180026926  mov     edx, esi; TokenInformationClass
0x180026928  mov     rcx, rbp; TokenHandle
0x18002692b  call    cs:__imp_GetTokenInformation
0x180026932  nop     dword ptr [rax+rax+00h]
0x180026937  test    eax, eax
0x180026939  jz      loc_180026A05
0x18002693f  xor     eax, eax
0x180026941  mov     [rdi], rbx
0x180026944  mov     rbx, [rsp+38h+arg_0]
0x180026949  mov     rbp, [rsp+38h+arg_8]
0x18002694e  mov     rsi, [rsp+38h+arg_10]
0x180026953  add     rsp, 30h
0x180026957  pop     rdi
0x180026958  retn
0x18002695a  mov     rcx, cs:WPP_GLOBAL_Control
0x180026961  lea     rdx, WPP_GLOBAL_Control
0x180026968  cmp     rcx, rdx
0x18002696b  jnz     short loc_180026983
0x18002696d  mov     rbp, [rsp+38h+arg_8]
0x180026972  mov     eax, 0Dh
0x180026977  mov     rsi, [rsp+38h+arg_10]
0x18002697c  add     rsp, 30h
0x180026980  pop     rdi
0x180026981  retn
0x180026983  test    byte ptr [rcx+1Ch], 1
0x180026987  jz      short loc_18002696D
0x180026989  mov     rcx, [rcx+10h]
0x18002698d  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x180026994  mov     edx, 1Dh
0x180026999  mov     r9d, 0Dh
0x18002699f  call    WPP_SF_d
0x1800269a4  jmp     short loc_18002696D
0x1800269a6  mov     ecx, 8; dwErrCode
0x1800269ab  call    cs:__imp_SetLastError
0x1800269b2  nop     dword ptr [rax+rax+00h]
0x1800269b7  call    cs:__imp_GetLastError
0x1800269be  nop     dword ptr [rax+rax+00h]
0x1800269c3  mov     ebx, eax
0x1800269c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269cc  lea     rdx, WPP_GLOBAL_Control
0x1800269d3  cmp     rcx, rdx
0x1800269d6  jz      loc_180026944
0x1800269dc  test    byte ptr [rcx+1Ch], 1
0x1800269e0  jz      loc_180026944
0x1800269e6  mov     rcx, [rcx+10h]
0x1800269ea  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x1800269f1  mov     edx, 1Eh
0x1800269f6  mov     r9d, eax
0x1800269f9  call    WPP_SF_d
0x1800269fe  mov     eax, ebx
0x180026a00  jmp     loc_180026944
0x180026a05  call    cs:__imp_GetLastError
0x180026a0c  nop     dword ptr [rax+rax+00h]
0x180026a11  mov     edi, eax
0x180026a13  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a1a  lea     rdx, WPP_GLOBAL_Control
0x180026a21  cmp     rcx, rdx
0x180026a24  jz      short loc_180026A44
0x180026a26  test    byte ptr [rcx+1Ch], 1
0x180026a2a  jz      short loc_180026A44
0x180026a2c  mov     rcx, [rcx+10h]
0x180026a30  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x180026a37  mov     edx, 1Fh
0x180026a3c  mov     r9d, eax
0x180026a3f  call    WPP_SF_d
0x180026a44  mov     rcx, gs:60h
0x180026a4d  mov     r8, rbx; P
0x180026a50  xor     edx, edx; Flags
0x180026a52  mov     rcx, [rcx+30h]; HeapHandle
0x180026a56  call    cs:__imp_RtlFreeHeap
0x180026a5d  nop     dword ptr [rax+rax+00h]
0x180026a62  mov     eax, edi
0x180026a64  jmp     loc_180026944
```
