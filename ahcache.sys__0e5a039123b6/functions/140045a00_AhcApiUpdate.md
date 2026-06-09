# AhcApiUpdate

- ea: `0x140045a00`
- end: `0x140045c30`
- name: `AhcApiUpdate`
- size: `560`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400497bc`

## callees

- `0x140003418`
- `0x140004553`
- `0x140007e40`
- `0x14003e364`
- `0x140043fc4`
- `0x140045a00`
- `0x140045d44`
- `0x140045d6c`
- `0x14004677c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140045bb8`
- `ntoskrnl!ZwClose` at `0x140045bb8`

## string_xrefs

- `0x140045a58`: `AhcApiUpdate`
- `0x140045b68`: `AhcApiUpdate`
- `0x140045b9d`: `AhcApiUpdate`
- `0x140045be9`: `AhcApiUpdate`
- `0x140045b57`: `Bad update buffer size [%x]`
- `0x140045b8c`: `Attempt to update without sufficient privileges [%x]`
- `0x140045c1e`: `Failed to update cache [%x]`
- `0x140045c08`: `Error copying memory [%x]`

## pseudocode

```c
__int64 __fastcall AhcApiUpdate(__int64 a1, unsigned int *a2)
{
  void *v4; // rbp
  int Key; // eax
  unsigned int v6; // ebx
  unsigned int v7; // r15d
  void *Pool2_0; // rax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  const char *v14; // r9
  __int64 v15; // r8
  bool v16; // zf
  HANDLE v17; // [rsp+20h] [rbp-38h]
  HANDLE v18; // [rsp+20h] [rbp-38h]
  int v19[10]; // [rsp+30h] [rbp-28h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp+20h] BYREF

  Handle = 0;
  *(_OWORD *)v19 = 0;
  if ( (int)AhcVerifyAdminContext() < 0 )
  {
    v16 = (*a2 & 0x5C0) == 0;
    *a2 &= 0x5C0u;
    if ( v16 )
    {
      v6 = -1073741790;
      AslLogCallPrintf(1, "AhcApiUpdate", 571, "Attempt to update without sufficient privileges [%x]", -1073741790);
      goto LABEL_12;
    }
  }
  v4 = 0;
  Key = AhcpApiGetKey((int)v19, (int)&Handle, (int)a2 + 8, (int)a2 + 32, *((HANDLE *)a2 + 3));
  v6 = Key;
  if ( Key < 0 )
  {
    LODWORD(v17) = Key;
    AslLogCallPrintf(1, "AhcApiUpdate", 586, "Failed to get key [%x]", v17);
    goto LABEL_8;
  }
  AslLogCallPrintf(3, "AhcApiUpdate", 590, "Got key %ws", *(_QWORD *)&v19[2]);
  v7 = a2[14];
  if ( v7 - 1 > 0xFFFF )
  {
    v6 = -1073741811;
    v14 = "Bad update buffer size [%x]";
    LODWORD(v18) = -1073741811;
    v15 = 598;
LABEL_16:
    AslLogCallPrintf(1, "AhcApiUpdate", v15, v14, v18);
    goto LABEL_8;
  }
  Pool2_0 = (void *)ExAllocatePool2_0(256, v7, 1953517633);
  v4 = Pool2_0;
  if ( !Pool2_0 )
  {
    v6 = -1073741801;
    AslLogCallPrintf(1, "AhcApiUpdate", 606, "Out of memory");
    goto LABEL_8;
  }
  v9 = AhcSafeCopyMemoryFromUserMode(Pool2_0, *((void **)a2 + 6), v7);
  v6 = v9;
  if ( v9 < 0 )
  {
    LODWORD(v18) = v9;
    v14 = "Error copying memory [%x]";
    v15 = 612;
    goto LABEL_16;
  }
  v10 = AhcCacheUpdate(a1, v19, Handle, *a2, v4, v7);
  v6 = v10;
  if ( v10 < 0 )
  {
    LODWORD(v18) = v10;
    v14 = "Failed to update cache [%x]";
    v15 = 623;
    goto LABEL_16;
  }
  v6 = 0;
LABEL_8:
  if ( Handle )
    ZwClose(Handle);
  if ( v4 )
    AslFree(v11, v4);
LABEL_12:
  if ( *(_QWORD *)&v19[2] )
  {
    memset(*(void **)&v19[2], 66, HIWORD(v19[0]));
    AslFree(v12, *(_QWORD *)&v19[2]);
  }
  return v6;
}

```

## disassembly

```asm
0x140045a00  mov     rax, rsp
0x140045a03  mov     [rax+8], rbx
0x140045a07  mov     [rax+10h], rbp
0x140045a0b  push    rdi
0x140045a0c  push    r12
0x140045a0e  push    r15
0x140045a10  sub     rsp, 40h
0x140045a14  xorps   xmm0, xmm0
0x140045a17  mov     qword ptr [rax+20h], 0
0x140045a1f  movups  xmmword ptr [rax-28h], xmm0
0x140045a23  mov     rdi, rdx
0x140045a26  mov     r12, rcx
0x140045a29  call    AhcVerifyAdminContext
0x140045a2e  test    eax, eax
0x140045a30  js      loc_140045B7B
0x140045a36  mov     rax, [rdi+18h]
0x140045a3a  lea     r9, [rdi+20h]; int
0x140045a3e  lea     r8, [rdi+8]; int
0x140045a42  mov     [rsp+58h+var_38], rax; Handle
0x140045a47  lea     rdx, [rsp+58h+Handle]; int
0x140045a4c  xor     ebp, ebp
0x140045a4e  lea     rcx, [rsp+58h+var_28]; int
0x140045a53  call    AhcpApiGetKey
0x140045a58  lea     rdx, aAhcapiupdate; "AhcApiUpdate"
0x140045a5f  mov     ebx, eax
0x140045a61  test    eax, eax
0x140045a63  js      loc_140045BC9
0x140045a69  mov     rax, [rsp+58h+var_20]
0x140045a6e  lea     r9, aGotKeyWs; "Got key %ws"
0x140045a75  mov     r8d, 24Eh
0x140045a7b  mov     [rsp+58h+var_38], rax
0x140045a80  lea     ecx, [rbp+3]
0x140045a83  call    AslLogCallPrintf
0x140045a88  mov     r15d, [rdi+38h]
0x140045a8c  lea     eax, [r15-1]
0x140045a90  cmp     eax, 0FFFFh
0x140045a95  ja      loc_140045B52
0x140045a9b  mov     r8d, 74705041h
0x140045aa1  mov     edx, r15d
0x140045aa4  mov     ecx, 100h
0x140045aa9  call    ExAllocatePool2_0
0x140045aae  mov     rbp, rax
0x140045ab1  test    rax, rax
0x140045ab4  jz      loc_140045BDC
0x140045aba  mov     rdx, [rdi+30h]; Src
0x140045abe  mov     r8d, r15d; Size
0x140045ac1  mov     rcx, rax; void *
0x140045ac4  call    AhcSafeCopyMemoryFromUserMode
0x140045ac9  mov     ebx, eax
0x140045acb  test    eax, eax
0x140045acd  js      loc_140045C04
0x140045ad3  mov     r9d, [rdi]
0x140045ad6  lea     rdx, [rsp+58h+var_28]
0x140045adb  mov     r8, [rsp+58h+Handle]
0x140045ae0  mov     rcx, r12
0x140045ae3  mov     [rsp+58h+var_30], r15d
0x140045ae8  mov     [rsp+58h+var_38], rbp
0x140045aed  call    AhcCacheUpdate
0x140045af2  mov     ebx, eax
0x140045af4  test    eax, eax
0x140045af6  js      loc_140045C1A
0x140045afc  xor     ebx, ebx
0x140045afe  cmp     [rsp+58h+Handle], 0
0x140045b04  jnz     loc_140045BB3
0x140045b0a  test    rbp, rbp
0x140045b0d  jz      short loc_140045B17
0x140045b0f  mov     rdx, rbp
0x140045b12  call    AslFree
0x140045b17  mov     rcx, [rsp+58h+var_20]; void *
0x140045b1c  test    rcx, rcx
0x140045b1f  jz      short loc_140045B3B
0x140045b21  movzx   r8d, word ptr [rsp+58h+var_28+2]; Size
0x140045b27  mov     edx, 42h ; 'B'; Val
0x140045b2c  call    memset
0x140045b31  mov     rdx, [rsp+58h+var_20]
0x140045b36  call    AslFree
0x140045b3b  mov     rbp, [rsp+58h+arg_8]
0x140045b40  mov     eax, ebx
0x140045b42  mov     rbx, [rsp+58h+arg_0]
0x140045b47  add     rsp, 40h
0x140045b4b  pop     r15
0x140045b4d  pop     r12
0x140045b4f  pop     rdi
0x140045b50  retn
0x140045b52  mov     ebx, 0C000000Dh
0x140045b57  lea     r9, aBadUpdateBuffe; "Bad update buffer size [%x]"
0x140045b5e  mov     dword ptr [rsp+58h+var_38], ebx
0x140045b62  mov     r8d, 256h
0x140045b68  lea     rdx, aAhcapiupdate; "AhcApiUpdate"
0x140045b6f  mov     ecx, 1
0x140045b74  call    AslLogCallPrintf
0x140045b79  jmp     short loc_140045AFE
0x140045b7b  and     dword ptr [rdi], 5C0h
0x140045b81  jnz     loc_140045A36
0x140045b87  mov     ebx, 0C0000022h
0x140045b8c  lea     r9, aAttemptToUpdat; "Attempt to update without sufficient pr"...
0x140045b93  mov     r8d, 23Bh
0x140045b99  mov     dword ptr [rsp+58h+var_38], ebx
0x140045b9d  lea     rdx, aAhcapiupdate; "AhcApiUpdate"
0x140045ba4  mov     ecx, 1
0x140045ba9  call    AslLogCallPrintf
0x140045bae  jmp     loc_140045B17
0x140045bb3  mov     rcx, [rsp+58h+Handle]; Handle
0x140045bb8  call    cs:__imp_ZwClose
0x140045bbf  nop     dword ptr [rax+rax+00h]
0x140045bc4  jmp     loc_140045B0A
0x140045bc9  mov     dword ptr [rsp+58h+var_38], eax
0x140045bcd  lea     r9, aFailedToGetKey_0; "Failed to get key [%x]"
0x140045bd4  mov     r8d, 24Ah
0x140045bda  jmp     short loc_140045B6F
0x140045bdc  lea     r9, aOutOfMemory; "Out of memory"
0x140045be3  mov     r8d, 25Eh
0x140045be9  lea     rdx, aAhcapiupdate; "AhcApiUpdate"
0x140045bf0  mov     ecx, 1
0x140045bf5  mov     ebx, 0C0000017h
0x140045bfa  call    AslLogCallPrintf
0x140045bff  jmp     loc_140045AFE
0x140045c04  mov     dword ptr [rsp+58h+var_38], eax
0x140045c08  lea     r9, aErrorCopyingMe; "Error copying memory [%x]"
0x140045c0f  mov     r8d, 264h
0x140045c15  jmp     loc_140045B68
0x140045c1a  mov     dword ptr [rsp+58h+var_38], eax
0x140045c1e  lea     r9, aFailedToUpdate_1; "Failed to update cache [%x]"
0x140045c25  mov     r8d, 26Fh
0x140045c2b  jmp     loc_140045B68
```
