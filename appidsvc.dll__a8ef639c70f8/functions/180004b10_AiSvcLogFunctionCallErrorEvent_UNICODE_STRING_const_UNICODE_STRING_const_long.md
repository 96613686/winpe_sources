# AiSvcLogFunctionCallErrorEvent(_UNICODE_STRING const *,_UNICODE_STRING const *,long)

- ea: `0x180004b10`
- end: `0x180004c21`
- name: `?AiSvcLogFunctionCallErrorEvent@@YAXPEBU_UNICODE_STRING@@0J@Z`
- size: `273`
- prototype: `void __fastcall(const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180004b10`
- `0x180008a34`
- `0x18000c0e0`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180004bca`
- `ntdll!EtwEventWriteTransfer` at `0x180004bca`

## pseudocode

```c
void __fastcall AiSvcLogFunctionCallErrorEvent(
        const struct _UNICODE_STRING *a1,
        const struct _UNICODE_STRING *a2,
        int a3)
{
  USHORT Length; // ax
  int v5; // edx
  int v6; // eax
  int v7; // r8d
  __int16 v8; // [rsp+30h] [rbp-19h] BYREF
  __int16 v9; // [rsp+34h] [rbp-15h] BYREF
  int v10; // [rsp+38h] [rbp-11h] BYREF
  _QWORD v11[3]; // [rsp+40h] [rbp-9h] BYREF
  int v12; // [rsp+58h] [rbp+Fh]
  int v13; // [rsp+5Ch] [rbp+13h]
  __int16 *v14; // [rsp+60h] [rbp+17h]
  __int64 v15; // [rsp+68h] [rbp+1Fh]
  PWSTR Buffer; // [rsp+70h] [rbp+27h]
  int v17; // [rsp+78h] [rbp+2Fh]
  int v18; // [rsp+7Ch] [rbp+33h]
  int *v19; // [rsp+80h] [rbp+37h]
  __int64 v20; // [rsp+88h] [rbp+3Fh]

  v10 = a3;
  Length = a1->Length;
  v12 = a1->Length;
  v5 = a2->Length;
  v8 = Length >> 1;
  v11[0] = &v8;
  v11[2] = a1->Buffer;
  v9 = (unsigned __int16)v5 >> 1;
  v14 = &v9;
  Buffer = a2->Buffer;
  v19 = &v10;
  v17 = v5;
  v11[1] = 2;
  v13 = 0;
  v15 = 2;
  v18 = 0;
  v20 = 4;
  v6 = EtwEventWriteTransfer(AiSvcEventHandle, AppIdFunctionCallError, 0, 0, 5, v11);
  if ( v6 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_ZDD(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)&WPP_GLOBAL_Control, v7, (_DWORD)a2, v10, v6);
}

```

## disassembly

```asm
0x180004b10  mov     [rsp-8+arg_0], rbx
0x180004b15  push    rbp
0x180004b16  lea     rbp, [rsp-57h]
0x180004b1b  sub     rsp, 0A0h
0x180004b22  mov     rax, cs:__security_cookie
0x180004b29  xor     rax, rsp
0x180004b2c  mov     [rbp+57h+var_10], rax
0x180004b30  mov     rbx, rdx
0x180004b33  mov     [rbp+57h+var_68], r8d
0x180004b37  movzx   edx, word ptr [rcx]
0x180004b3a  xor     r9d, r9d
0x180004b3d  movzx   eax, dx
0x180004b40  mov     [rbp+57h+var_48], edx
0x180004b43  shr     ax, 1
0x180004b46  xor     r8d, r8d
0x180004b49  movzx   edx, word ptr [rbx]
0x180004b4c  mov     [rbp+57h+var_70], ax
0x180004b50  lea     rax, [rbp+57h+var_70]
0x180004b54  mov     [rbp+57h+var_60], rax
0x180004b58  mov     rax, [rcx+8]
0x180004b5c  mov     rcx, cs:?AiSvcEventHandle@@3_KA; unsigned __int64 AiSvcEventHandle
0x180004b63  mov     [rbp+57h+var_50], rax
0x180004b67  movzx   eax, dx
0x180004b6a  shr     ax, 1
0x180004b6d  mov     [rbp+57h+var_6C], ax
0x180004b71  lea     rax, [rbp+57h+var_6C]
0x180004b75  mov     [rbp+57h+var_40], rax
0x180004b79  mov     rax, [rbx+8]
0x180004b7d  mov     [rbp+57h+var_30], rax
0x180004b81  lea     rax, [rbp+57h+var_68]
0x180004b85  mov     [rbp+57h+var_20], rax
0x180004b89  lea     rax, [rbp+57h+var_60]
0x180004b8d  mov     [rbp+57h+var_28], edx
0x180004b90  lea     rdx, AppIdFunctionCallError
0x180004b97  mov     [rsp+0A0h+var_78], rax
0x180004b9c  mov     [rsp+0A0h+var_80], 5
0x180004ba4  mov     [rbp+57h+var_58], 2
0x180004bac  mov     [rbp+57h+var_44], 0
0x180004bb3  mov     [rbp+57h+var_38], 2
0x180004bbb  mov     [rbp+57h+var_24], 0
0x180004bc2  mov     [rbp+57h+var_18], 4
0x180004bca  call    cs:__imp_EtwEventWriteTransfer
0x180004bd0  test    eax, eax
0x180004bd2  jns     short loc_180004C04
0x180004bd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bdb  lea     rdx, WPP_GLOBAL_Control
0x180004be2  cmp     rcx, rdx
0x180004be5  jz      short loc_180004C04
0x180004be7  test    byte ptr [rcx+1Ch], 4
0x180004beb  jz      short loc_180004C04
0x180004bed  mov     rcx, [rcx+10h]
0x180004bf1  mov     r9, rbx
0x180004bf4  mov     dword ptr [rsp+0A0h+var_78], eax
0x180004bf8  mov     eax, [rbp+57h+var_68]
0x180004bfb  mov     [rsp+0A0h+var_80], eax
0x180004bff  call    WPP_SF_ZDD
0x180004c04  mov     rcx, [rbp+57h+var_10]
0x180004c08  xor     rcx, rsp; StackCookie
0x180004c0b  call    __security_check_cookie
0x180004c10  mov     rbx, [rsp+0A0h+arg_0]
0x180004c18  add     rsp, 0A0h
0x180004c1f  pop     rbp
0x180004c20  retn
```
