# Task_ProbePartner

- ea: `0x140017a48`
- end: `0x140017aff`
- name: `Task_ProbePartner`
- size: `183`
- prototype: `__int64 __fastcall(__int64, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140017b08`

## callees

- `0x140017a48`
- `0x140019b28`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140017ae4`
- `KERNEL32!SetLastError` at `0x140017ae4`
- `KERNEL32!WaitForSingleObjectEx` at `0x140017a79`
- `KERNEL32!WaitForSingleObjectEx` at `0x140017abe`
- `KERNEL32!WaitForSingleObjectEx` at `0x140017a79`
- `KERNEL32!WaitForSingleObjectEx` at `0x140017abe`

## pseudocode

```c
__int64 __fastcall Task_ProbePartner(__int64 a1, int *a2, unsigned int *a3)
{
  unsigned int v3; // edi
  int v4; // ebp
  DWORD v8; // ecx
  DWORD v9; // eax
  unsigned int v10; // ebx
  unsigned int ExitCode; // eax
  DWORD v12; // eax
  __int64 result; // rax
  unsigned int v14; // [rsp+60h] [rbp+8h] BYREF

  v3 = 0;
  v4 = 0;
  v14 = 0;
  if ( !a1 )
  {
    v8 = 87;
LABEL_14:
    v10 = 0;
    SetLastError(v8);
    goto LABEL_15;
  }
  v9 = WaitForSingleObjectEx(*(HANDLE *)(a1 + 32), 0, 0);
  if ( v9 == -1 )
    goto LABEL_4;
  if ( v9 )
  {
    v10 = 1;
    if ( v9 != 258 )
      goto LABEL_13;
  }
  else
  {
    v4 = 1;
    ExitCode = GetExitCode(*(HANDLE *)(a1 + 32), &v14);
    v3 = v14;
    v10 = ExitCode;
    if ( !ExitCode )
      goto LABEL_15;
  }
  v12 = WaitForSingleObjectEx(*(HANDLE *)(a1 + 24), 0, 0);
  if ( v12 != -1 )
  {
    if ( v12 == 258 )
    {
      v4 = 1;
      v3 = 0;
      goto LABEL_15;
    }
    if ( !v12 )
      goto LABEL_15;
LABEL_13:
    v8 = 1359;
    goto LABEL_14;
  }
LABEL_4:
  v10 = 0;
LABEL_15:
  *a2 = v4;
  result = v10;
  *a3 = v3;
  return result;
}

```

## disassembly

```asm
0x140017a48  push    rbx
0x140017a4a  push    rbp
0x140017a4b  push    rsi
0x140017a4c  push    rdi
0x140017a4d  push    r14
0x140017a4f  push    r15
0x140017a51  sub     rsp, 28h
0x140017a55  xor     edi, edi
0x140017a57  xor     ebp, ebp
0x140017a59  mov     [rsp+58h+arg_0], edi
0x140017a5d  mov     r14, r8
0x140017a60  mov     r15, rdx
0x140017a63  mov     rsi, rcx
0x140017a66  test    rcx, rcx
0x140017a69  jnz     short loc_140017A70
0x140017a6b  lea     ecx, [rsi+57h]
0x140017a6e  jmp     short loc_140017AE2
0x140017a70  mov     rcx, [rcx+20h]; hHandle
0x140017a74  xor     r8d, r8d; bAlertable
0x140017a77  xor     edx, edx; dwMilliseconds
0x140017a79  call    cs:__imp_WaitForSingleObjectEx
0x140017a7f  cmp     eax, 0FFFFFFFFh
0x140017a82  jnz     short loc_140017A88
0x140017a84  xor     ebx, ebx
0x140017a86  jmp     short loc_140017AEA
0x140017a88  test    eax, eax
0x140017a8a  jnz     short loc_140017AA9
0x140017a8c  mov     rcx, [rsi+20h]; hProcess
0x140017a90  lea     rdx, [rsp+58h+arg_0]; unsigned int *
0x140017a95  lea     ebp, [rax+1]
0x140017a98  call    ?GetExitCode@@YAHPEAXPEAK@Z; GetExitCode(void *,ulong *)
0x140017a9d  mov     edi, [rsp+58h+arg_0]
0x140017aa1  mov     ebx, eax
0x140017aa3  test    eax, eax
0x140017aa5  jnz     short loc_140017AB5
0x140017aa7  jmp     short loc_140017AEA
0x140017aa9  mov     ebx, 1
0x140017aae  cmp     eax, 102h
0x140017ab3  jnz     short loc_140017ADD
0x140017ab5  mov     rcx, [rsi+18h]; hHandle
0x140017ab9  xor     r8d, r8d; bAlertable
0x140017abc  xor     edx, edx; dwMilliseconds
0x140017abe  call    cs:__imp_WaitForSingleObjectEx
0x140017ac4  cmp     eax, 0FFFFFFFFh
0x140017ac7  jz      short loc_140017A84
0x140017ac9  cmp     eax, 102h
0x140017ace  jnz     short loc_140017AD9
0x140017ad0  mov     ebp, 1
0x140017ad5  xor     edi, edi
0x140017ad7  jmp     short loc_140017AEA
0x140017ad9  test    eax, eax
0x140017adb  jz      short loc_140017AEA
0x140017add  mov     ecx, 54Fh; dwErrCode
0x140017ae2  xor     ebx, ebx
0x140017ae4  call    cs:__imp_SetLastError
0x140017aea  mov     [r15], ebp
0x140017aed  mov     eax, ebx
0x140017aef  mov     [r14], edi
0x140017af2  add     rsp, 28h
0x140017af6  pop     r15
0x140017af8  pop     r14
0x140017afa  pop     rdi
0x140017afb  pop     rsi
0x140017afc  pop     rbp
0x140017afd  pop     rbx
0x140017afe  retn
```
