# NgscbpGetBcdIsSlateDevice

- ea: `0x180069d50`
- end: `0x180069ec8`
- name: `NgscbpGetBcdIsSlateDevice`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180069ed0`

## callees

- `0x180009f60`
- `0x18001b890`
- `0x180069d50`

## import_xrefs

- `bcd!BcdOpenSystemStore` at `0x180069d84`
- `bcd!BcdOpenSystemStore` at `0x180069d84`
- `bcd!BcdOpenObject` at `0x180069de5`
- `bcd!BcdOpenObject` at `0x180069de5`
- `bcd!BcdCloseStore` at `0x180069eab`
- `bcd!BcdCloseStore` at `0x180069eab`
- `bcd!BcdGetElementData` at `0x180069e3d`
- `bcd!BcdGetElementData` at `0x180069e3d`
- `bcd!BcdCloseObject` at `0x180069e96`
- `bcd!BcdCloseObject` at `0x180069e96`

## pseudocode

```c
__int64 __fastcall NgscbpGetBcdIsSlateDevice(bool *a1)
{
  int v2; // eax
  unsigned int v3; // eax
  int v4; // ebx
  int v5; // eax
  unsigned int v6; // eax
  int ElementData; // eax
  unsigned int v8; // eax
  __int64 v10; // [rsp+20h] [rbp-10h] BYREF
  __int16 v11; // [rsp+58h] [rbp+28h] BYREF
  int v12; // [rsp+60h] [rbp+30h] BYREF
  __int64 v13; // [rsp+68h] [rbp+38h] BYREF

  v10 = 0;
  v13 = 0;
  v11 = 0;
  v12 = 2;
  v2 = BcdOpenSystemStore(&v10);
  v3 = FromNtStatus(v2);
  v4 = v3;
  if ( !v3 )
    goto LABEL_6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v3);
  if ( v4 >= 0 )
  {
LABEL_6:
    v5 = BcdOpenObject(v10, &GUID_WINDOWS_BOOTMGR, &v13);
    v6 = FromNtStatus(v5);
    v4 = v6;
    if ( !v6 )
      goto LABEL_11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v6);
    if ( v4 >= 0 )
    {
LABEL_11:
      ElementData = BcdGetElementData(v13, 369098866, &v11, &v12);
      v8 = FromNtStatus(ElementData);
      v4 = v8;
      if ( !v8 )
        goto LABEL_16;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v8);
      if ( v4 >= 0 )
LABEL_16:
        *a1 = (_BYTE)v11 != 0;
    }
  }
  if ( v13 )
    BcdCloseObject(v13);
  if ( v10 )
    BcdCloseStore(v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180069d50  mov     [rsp-18h+arg_0], rbx
0x180069d55  push    rbp
0x180069d56  push    rdi
0x180069d57  push    r15
0x180069d59  mov     rbp, rsp
0x180069d5c  sub     rsp, 30h
0x180069d60  mov     rdi, rcx
0x180069d63  mov     [rbp+var_10], 0
0x180069d6b  xor     eax, eax
0x180069d6d  mov     [rbp+arg_18], 0
0x180069d75  lea     rcx, [rbp+var_10]
0x180069d79  mov     [rbp+arg_8], ax
0x180069d7d  mov     [rbp+arg_10], 2
0x180069d84  call    cs:__imp_BcdOpenSystemStore
0x180069d8b  nop     dword ptr [rax+rax+00h]
0x180069d90  mov     ecx, eax; int
0x180069d92  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180069d97  lea     r15, WPP_GLOBAL_Control
0x180069d9e  mov     ebx, eax
0x180069da0  test    eax, eax
0x180069da2  jz      short loc_180069DD6
0x180069da4  mov     rcx, cs:WPP_GLOBAL_Control
0x180069dab  cmp     rcx, r15
0x180069dae  jz      short loc_180069DCE
0x180069db0  test    byte ptr [rcx+1Ch], 40h
0x180069db4  jz      short loc_180069DCE
0x180069db6  mov     rcx, [rcx+10h]
0x180069dba  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180069dc1  mov     edx, 11h
0x180069dc6  mov     r9d, eax
0x180069dc9  call    WPP_SF_d
0x180069dce  test    ebx, ebx
0x180069dd0  js      loc_180069E8D
0x180069dd6  mov     rcx, [rbp+var_10]
0x180069dda  lea     r8, [rbp+arg_18]
0x180069dde  lea     rdx, GUID_WINDOWS_BOOTMGR
0x180069de5  call    cs:__imp_BcdOpenObject
0x180069dec  nop     dword ptr [rax+rax+00h]
0x180069df1  mov     ecx, eax; int
0x180069df3  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180069df8  mov     ebx, eax
0x180069dfa  test    eax, eax
0x180069dfc  jz      short loc_180069E2C
0x180069dfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180069e05  cmp     rcx, r15
0x180069e08  jz      short loc_180069E28
0x180069e0a  test    byte ptr [rcx+1Ch], 40h
0x180069e0e  jz      short loc_180069E28
0x180069e10  mov     rcx, [rcx+10h]
0x180069e14  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180069e1b  mov     edx, 12h
0x180069e20  mov     r9d, eax
0x180069e23  call    WPP_SF_d
0x180069e28  test    ebx, ebx
0x180069e2a  js      short loc_180069E8D
0x180069e2c  mov     rcx, [rbp+arg_18]
0x180069e30  lea     r9, [rbp+arg_10]
0x180069e34  lea     r8, [rbp+arg_8]
0x180069e38  mov     edx, 16000072h
0x180069e3d  call    cs:__imp_BcdGetElementData
0x180069e44  nop     dword ptr [rax+rax+00h]
0x180069e49  mov     ecx, eax; int
0x180069e4b  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180069e50  mov     ebx, eax
0x180069e52  test    eax, eax
0x180069e54  jz      short loc_180069E84
0x180069e56  mov     rcx, cs:WPP_GLOBAL_Control
0x180069e5d  cmp     rcx, r15
0x180069e60  jz      short loc_180069E80
0x180069e62  test    byte ptr [rcx+1Ch], 40h
0x180069e66  jz      short loc_180069E80
0x180069e68  mov     rcx, [rcx+10h]
0x180069e6c  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180069e73  mov     edx, 13h
0x180069e78  mov     r9d, eax
0x180069e7b  call    WPP_SF_d
0x180069e80  test    ebx, ebx
0x180069e82  js      short loc_180069E8D
0x180069e84  cmp     byte ptr [rbp+arg_8], 0
0x180069e88  setnz   al
0x180069e8b  mov     [rdi], al
0x180069e8d  mov     rcx, [rbp+arg_18]
0x180069e91  test    rcx, rcx
0x180069e94  jz      short loc_180069EA2
0x180069e96  call    cs:__imp_BcdCloseObject
0x180069e9d  nop     dword ptr [rax+rax+00h]
0x180069ea2  mov     rcx, [rbp+var_10]
0x180069ea6  test    rcx, rcx
0x180069ea9  jz      short loc_180069EB7
0x180069eab  call    cs:__imp_BcdCloseStore
0x180069eb2  nop     dword ptr [rax+rax+00h]
0x180069eb7  mov     eax, ebx
0x180069eb9  mov     rbx, [rsp+30h+arg_0]
0x180069ebe  add     rsp, 30h
0x180069ec2  pop     r15
0x180069ec4  pop     rdi
0x180069ec5  pop     rbp
0x180069ec6  retn
```
