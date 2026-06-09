# BfspPopulateNewBcdStore

- ea: `0x140007cdc`
- end: `0x140007e18`
- name: `BfspPopulateNewBcdStore`
- size: `316`
- prototype: `__int64 __fastcall(__int64, __int64, GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140004080`

## callees

- `0x1400052bc`
- `0x14000583c`
- `0x1400058e4`
- `0x140005ae8`
- `0x140005b98`
- `0x140005fc4`
- `0x140007cdc`
- `0x140008104`
- `0x14000e628`
- `0x140026650`

## string_xrefs

- `0x140007ddd`: `Failed to create create {bootmgr} object. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspPopulateNewBcdStore(__int64 a1, __int64 a2, GUID *a3)
{
  int GeneralObjects; // ebx
  __int128 *v7; // r14
  int v8; // eax
  GUID v10; // [rsp+20h] [rbp-58h] BYREF
  __int128 v11; // [rsp+30h] [rbp-48h] BYREF

  v10 = 0;
  v11 = 0;
  if ( (dword_14003F8FC & 0x40) != 0 && a3 )
    v10 = *a3;
  GeneralObjects = BfspCreateGeneralObjects(a1, a2);
  if ( GeneralObjects >= 0 )
  {
    v7 = 0;
    if ( (dword_14003F8FC & 1) == 0 )
    {
      GeneralObjects = BfspCreateResumeObject(a1, a2, &v10, (__int64)&v11);
      if ( GeneralObjects < 0 )
        return (unsigned int)GeneralObjects;
      v7 = &v11;
    }
    GeneralObjects = BfspCreateMemtestObject(a1, a2);
    if ( GeneralObjects >= 0 )
    {
      GeneralObjects = BfspCreateOsLoaderObject(a1, a2, (__int64)v7, (__int128 *)&v10);
      if ( GeneralObjects >= 0 )
      {
        if ( (dword_14003F8FC & 2) == 0 || (GeneralObjects = BfspCreateNtldrObject(a1, a2), GeneralObjects >= 0) )
        {
          GeneralObjects = BfspRemoveDuplicateEntries(a2, &v10);
          if ( GeneralObjects >= 0 )
          {
            v8 = BfspCreateBootmgrObject(a1, a2, (__int64)v7, &v10);
            GeneralObjects = v8;
            if ( v8 >= 0 )
            {
              if ( a3 )
                *a3 = v10;
            }
            else
            {
              BfspLogMessage(4, L"Failed to create create {bootmgr} object. Status = [%x]", (unsigned int)v8);
            }
          }
        }
      }
    }
  }
  return (unsigned int)GeneralObjects;
}

```

## disassembly

```asm
0x140007cdc  push    rbx
0x140007cde  push    rbp
0x140007cdf  push    rsi
0x140007ce0  push    rdi
0x140007ce1  push    r14
0x140007ce3  sub     rsp, 50h
0x140007ce7  mov     rax, cs:__security_cookie
0x140007cee  xor     rax, rsp
0x140007cf1  mov     [rsp+78h+var_38], rax
0x140007cf6  test    byte ptr cs:dword_14003F8FC, 40h
0x140007cfd  xorps   xmm0, xmm0
0x140007d00  xorps   xmm1, xmm1
0x140007d03  mov     rsi, r8
0x140007d06  movups  [rsp+78h+var_58], xmm0
0x140007d0b  mov     rdi, rdx
0x140007d0e  mov     rbp, rcx
0x140007d11  movups  [rsp+78h+var_48], xmm1
0x140007d16  jz      short loc_140007D27
0x140007d18  test    r8, r8
0x140007d1b  jz      short loc_140007D27
0x140007d1d  movups  xmm0, xmmword ptr [r8]
0x140007d21  movdqu  [rsp+78h+var_58], xmm0
0x140007d27  call    BfspCreateGeneralObjects
0x140007d2c  mov     ebx, eax
0x140007d2e  test    eax, eax
0x140007d30  js      loc_140007DFE
0x140007d36  xor     r14d, r14d
0x140007d39  test    byte ptr cs:dword_14003F8FC, 1
0x140007d40  jnz     short loc_140007D66
0x140007d42  lea     r9, [rsp+78h+var_48]
0x140007d47  mov     rdx, rdi
0x140007d4a  lea     r8, [rsp+78h+var_58]
0x140007d4f  mov     rcx, rbp
0x140007d52  call    BfspCreateResumeObject
0x140007d57  mov     ebx, eax
0x140007d59  test    eax, eax
0x140007d5b  js      loc_140007DFE
0x140007d61  lea     r14, [rsp+78h+var_48]
0x140007d66  mov     rdx, rdi
0x140007d69  mov     rcx, rbp
0x140007d6c  call    BfspCreateMemtestObject
0x140007d71  mov     ebx, eax
0x140007d73  test    eax, eax
0x140007d75  js      loc_140007DFE
0x140007d7b  lea     r9, [rsp+78h+var_58]
0x140007d80  mov     r8, r14
0x140007d83  mov     rdx, rdi
0x140007d86  mov     rcx, rbp
0x140007d89  call    BfspCreateOsLoaderObject
0x140007d8e  mov     ebx, eax
0x140007d90  test    eax, eax
0x140007d92  js      short loc_140007DFE
0x140007d94  test    byte ptr cs:dword_14003F8FC, 2
0x140007d9b  jz      short loc_140007DAE
0x140007d9d  mov     rdx, rdi
0x140007da0  mov     rcx, rbp
0x140007da3  call    BfspCreateNtldrObject
0x140007da8  mov     ebx, eax
0x140007daa  test    eax, eax
0x140007dac  js      short loc_140007DFE
0x140007dae  lea     rdx, [rsp+78h+var_58]
0x140007db3  mov     rcx, rdi
0x140007db6  call    BfspRemoveDuplicateEntries
0x140007dbb  mov     ebx, eax
0x140007dbd  test    eax, eax
0x140007dbf  js      short loc_140007DFE
0x140007dc1  lea     r9, [rsp+78h+var_58]
0x140007dc6  mov     r8, r14
0x140007dc9  mov     rdx, rdi
0x140007dcc  mov     rcx, rbp
0x140007dcf  call    BfspCreateBootmgrObject
0x140007dd4  mov     ebx, eax
0x140007dd6  test    eax, eax
0x140007dd8  jns     short loc_140007DF0
0x140007dda  mov     r8d, eax
0x140007ddd  lea     rdx, aFailedToCreate_1; "Failed to create create {bootmgr} objec"...
0x140007de4  mov     ecx, 4
0x140007de9  call    BfspLogMessage
0x140007dee  jmp     short loc_140007DFE
0x140007df0  test    rsi, rsi
0x140007df3  jz      short loc_140007DFE
0x140007df5  movups  xmm0, [rsp+78h+var_58]
0x140007dfa  movdqu  xmmword ptr [rsi], xmm0
0x140007dfe  mov     eax, ebx
0x140007e00  mov     rcx, [rsp+78h+var_38]
0x140007e05  xor     rcx, rsp; StackCookie
0x140007e08  call    __security_check_cookie
0x140007e0d  add     rsp, 50h
0x140007e11  pop     r14
0x140007e13  pop     rdi
0x140007e14  pop     rsi
0x140007e15  pop     rbp
0x140007e16  pop     rbx
0x140007e17  retn
```
