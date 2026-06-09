# VfsMessageCommonValidate

- ea: `0x140009b0c`
- end: `0x140009d3b`
- name: `VfsMessageCommonValidate`
- size: `559`
- prototype: `NTSTATUS __fastcall(__int64, unsigned int, unsigned int *, GUID *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009784`
- `0x140009d44`

## callees

- `0x140009b0c`
- `0x140013b00`

## import_xrefs

- `ntoskrnl!RtlGUIDFromString` at `0x140009c39`
- `ntoskrnl!RtlGUIDFromString` at `0x140009c9a`
- `ntoskrnl!RtlGUIDFromString` at `0x140009c39`
- `ntoskrnl!RtlGUIDFromString` at `0x140009c9a`
- `ntoskrnl!RtlValidSid` at `0x140009ce0`
- `ntoskrnl!RtlValidSid` at `0x140009ce0`

## pseudocode

```c
NTSTATUS __fastcall VfsMessageCommonValidate(__int64 a1, unsigned int a2, unsigned int *a3, GUID *a4, _QWORD *a5)
{
  unsigned int v8; // eax
  unsigned int v9; // esi
  __int64 v10; // rdx
  int v11; // ecx
  __int64 v12; // rdi
  NTSTATUS result; // eax
  GUID v14; // xmm6
  GUID v15; // xmm7
  unsigned __int16 v16; // ax
  void *v17; // rdi
  UNICODE_STRING GuidString_8; // [rsp+28h] [rbp-B1h] BYREF
  UNICODE_STRING v19; // [rsp+38h] [rbp-A1h] BYREF
  GUID Guid_8; // [rsp+48h] [rbp-91h] BYREF
  GUID v21[2]; // [rsp+58h] [rbp-81h] BYREF
  __int16 v22; // [rsp+78h] [rbp-61h] BYREF
  __int128 v23; // [rsp+7Ah] [rbp-5Fh]
  __int128 v24; // [rsp+8Ah] [rbp-4Fh]
  __int128 v25; // [rsp+9Ah] [rbp-3Fh]
  __int128 v26; // [rsp+AAh] [rbp-2Fh]
  __int64 v27; // [rsp+BAh] [rbp-1Fh]
  __int16 v28; // [rsp+C2h] [rbp-17h]

  v21[1] = 0;
  if ( a2 < 0x1C )
    return -1073741811;
  v8 = *(_DWORD *)a1;
  if ( a2 < *(_DWORD *)a1 )
    return -1073741811;
  if ( v8 < 0x1C )
    return -1073741811;
  v9 = v8 - 24;
  if ( *(unsigned __int16 *)(a1 + 16) + (unsigned int)*(unsigned __int16 *)(a1 + 18) > v8 - 24 )
    return -1073741811;
  v10 = *(unsigned __int16 *)(a1 + 12);
  v11 = *(unsigned __int16 *)(a1 + 14);
  if ( (int)v10 + v11 > v9 )
    return -1073741811;
  v12 = (unsigned int)v10;
  if ( v11 == 32 )
  {
    v14 = *(GUID *)(v10 + a1 + 24);
    v15 = *(GUID *)(v10 + a1 + 40);
    goto LABEL_13;
  }
  GuidString_8 = 0;
  v19 = 0;
  Guid_8 = 0;
  v21[0] = 0;
  if ( (v11 & 0xFFFE) != 0x92 || *(_WORD *)(v10 + a1 + 96) != 95 )
    return -1073741811;
  *(_DWORD *)&GuidString_8.Length = 4980812;
  v22 = 123;
  v28 = 125;
  GuidString_8.Buffer = (wchar_t *)&v22;
  v23 = *(_OWORD *)(v10 + a1 + 24);
  v24 = *(_OWORD *)(v10 + a1 + 40);
  v25 = *(_OWORD *)(v10 + a1 + 56);
  v26 = *(_OWORD *)(v10 + a1 + 72);
  v27 = *(_QWORD *)(v10 + a1 + 88);
  result = RtlGUIDFromString(&GuidString_8, &Guid_8);
  if ( result >= 0 )
  {
    v19 = GuidString_8;
    v23 = *(_OWORD *)(v12 + a1 + 98);
    v24 = *(_OWORD *)(v12 + a1 + 114);
    v25 = *(_OWORD *)(v12 + a1 + 130);
    v26 = *(_OWORD *)(v12 + a1 + 146);
    v27 = *(_QWORD *)(v12 + a1 + 162);
    result = RtlGUIDFromString(&v19, v21);
    if ( result >= 0 )
    {
      v14 = Guid_8;
      v15 = v21[0];
LABEL_13:
      v16 = *(_WORD *)(a1 + 18);
      v17 = 0;
      if ( !v16 || v16 <= 0x44u && (v17 = (void *)(a1 + *(unsigned __int16 *)(a1 + 16) + 24LL), RtlValidSid(v17)) )
      {
        *a3 = v9;
        result = 0;
        *a4 = v14;
        a4[1] = v15;
        *a5 = v17;
        return result;
      }
      return -1073741811;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140009b0c  mov     rax, rsp
0x140009b0f  mov     [rax+10h], rbx
0x140009b13  push    rbp
0x140009b14  push    rsi
0x140009b15  push    rdi
0x140009b16  push    r12
0x140009b18  push    r13
0x140009b1a  push    r14
0x140009b1c  push    r15
0x140009b1e  lea     rbp, [rax-57h]
0x140009b22  sub     rsp, 0F0h
0x140009b29  movaps  xmmword ptr [rax-48h], xmm6
0x140009b2d  movaps  xmmword ptr [rax-58h], xmm7
0x140009b31  mov     rax, cs:__security_cookie
0x140009b38  xor     rax, rsp
0x140009b3b  mov     [rbp+4Fh+var_60], rax
0x140009b3f  mov     r12, [rbp+4Fh+arg_20]
0x140009b43  xorps   xmm0, xmm0
0x140009b46  mov     r14, r9
0x140009b49  mov     r15, r8
0x140009b4c  mov     rbx, rcx
0x140009b4f  movdqu  [rbp+4Fh+var_C0], xmm0
0x140009b54  cmp     edx, 1Ch
0x140009b57  jb      loc_140009D04
0x140009b5d  mov     eax, [rcx]
0x140009b5f  cmp     edx, eax
0x140009b61  jb      loc_140009D04
0x140009b67  cmp     eax, 1Ch
0x140009b6a  jb      loc_140009D04
0x140009b70  movzx   ecx, word ptr [rcx+12h]
0x140009b74  lea     esi, [rax-18h]
0x140009b77  movzx   eax, word ptr [rbx+10h]
0x140009b7b  add     ecx, eax
0x140009b7d  cmp     ecx, esi
0x140009b7f  ja      loc_140009D04
0x140009b85  movzx   edx, word ptr [rbx+0Ch]
0x140009b89  movzx   ecx, word ptr [rbx+0Eh]
0x140009b8d  lea     eax, [rdx+rcx]
0x140009b90  cmp     eax, esi
0x140009b92  ja      loc_140009D04
0x140009b98  xor     r13d, r13d
0x140009b9b  mov     edi, edx
0x140009b9d  cmp     ecx, 20h ; ' '
0x140009ba0  jz      loc_140009CB6
0x140009ba6  mov     eax, 0FFFEh
0x140009bab  xorps   xmm1, xmm1
0x140009bae  and     cx, ax
0x140009bb1  mov     eax, 92h
0x140009bb6  movups  xmmword ptr [rsp+120h+GuidString.Buffer], xmm0
0x140009bbb  movups  xmmword ptr [rsp+120h+var_F8.Buffer], xmm1
0x140009bc0  movups  xmmword ptr [rsp+120h+Guid.Data4], xmm0
0x140009bc5  movups  xmmword ptr [rsp+120h+var_D8.Data4], xmm1
0x140009bca  cmp     cx, ax
0x140009bcd  jnz     loc_140009D04
0x140009bd3  cmp     word ptr [rdx+rbx+60h], 5Fh ; '_'
0x140009bd9  jnz     loc_140009D04
0x140009bdf  mov     dword ptr [rsp+120h+GuidString.Buffer], 4C004Ch
0x140009be7  lea     eax, [r13+7Bh]
0x140009beb  mov     [rbp+4Fh+var_B0], ax
0x140009bef  lea     rcx, [rsp+120h+GuidString.Buffer]; GuidString
0x140009bf4  lea     eax, [r13+7Dh]
0x140009bf8  mov     [rbp+4Fh+var_66], ax
0x140009bfc  lea     rax, [rbp+4Fh+var_B0]
0x140009c00  mov     qword ptr [rsp+120h+var_F8.Length], rax
0x140009c05  movups  xmm0, xmmword ptr [rdx+rbx+18h]
0x140009c0a  movups  [rbp+4Fh+var_AE], xmm0
0x140009c0e  movups  xmm1, xmmword ptr [rdx+rbx+28h]
0x140009c13  movups  [rbp+4Fh+var_9E], xmm1
0x140009c17  movups  xmm0, xmmword ptr [rdx+rbx+38h]
0x140009c1c  movups  [rbp+4Fh+var_8E], xmm0
0x140009c20  movups  xmm1, xmmword ptr [rdx+rbx+48h]
0x140009c25  movups  [rbp+4Fh+var_7E], xmm1
0x140009c29  movsd   xmm0, qword ptr [rdx+rbx+58h]
0x140009c2f  lea     rdx, [rsp+120h+Guid.Data4]; Guid
0x140009c34  movsd   [rbp+4Fh+var_6E], xmm0
0x140009c39  call    cs:__imp_RtlGUIDFromString
0x140009c40  nop     dword ptr [rax+rax+00h]
0x140009c45  test    eax, eax
0x140009c47  js      loc_140009D09
0x140009c4d  movaps  xmm0, xmmword ptr [rsp+120h+GuidString.Buffer]
0x140009c52  lea     rdx, [rsp+120h+var_D8.Data4]; Guid
0x140009c57  movdqa  xmmword ptr [rsp+120h+var_F8.Buffer], xmm0
0x140009c5d  lea     rcx, [rsp+120h+var_F8.Buffer]; GuidString
0x140009c62  movups  xmm1, xmmword ptr [rdi+rbx+62h]
0x140009c67  movups  [rbp+4Fh+var_AE], xmm1
0x140009c6b  movups  xmm0, xmmword ptr [rdi+rbx+72h]
0x140009c70  movups  [rbp+4Fh+var_9E], xmm0
0x140009c74  movups  xmm1, xmmword ptr [rdi+rbx+82h]
0x140009c7c  movups  [rbp+4Fh+var_8E], xmm1
0x140009c80  movups  xmm0, xmmword ptr [rdi+rbx+92h]
0x140009c88  movups  [rbp+4Fh+var_7E], xmm0
0x140009c8c  movsd   xmm1, qword ptr [rdi+rbx+0A2h]
0x140009c95  movsd   [rbp+4Fh+var_6E], xmm1
0x140009c9a  call    cs:__imp_RtlGUIDFromString
0x140009ca1  nop     dword ptr [rax+rax+00h]
0x140009ca6  test    eax, eax
0x140009ca8  js      short loc_140009D09
0x140009caa  movups  xmm6, xmmword ptr [rsp+120h+Guid.Data4]
0x140009caf  movups  xmm7, xmmword ptr [rsp+120h+var_D8.Data4]
0x140009cb4  jmp     short loc_140009CC0
0x140009cb6  movups  xmm6, xmmword ptr [rdx+rbx+18h]
0x140009cbb  movups  xmm7, xmmword ptr [rdx+rbx+28h]
0x140009cc0  movzx   eax, word ptr [rbx+12h]
0x140009cc4  mov     rdi, r13
0x140009cc7  test    ax, ax
0x140009cca  jz      short loc_140009CF0
0x140009ccc  cmp     ax, 44h ; 'D'
0x140009cd0  ja      short loc_140009D04
0x140009cd2  movzx   edi, word ptr [rbx+10h]
0x140009cd6  add     rdi, 18h
0x140009cda  add     rdi, rbx
0x140009cdd  mov     rcx, rdi; Sid
0x140009ce0  call    cs:__imp_RtlValidSid
0x140009ce7  nop     dword ptr [rax+rax+00h]
0x140009cec  test    al, al
0x140009cee  jz      short loc_140009D04
0x140009cf0  mov     [r15], esi
0x140009cf3  xor     eax, eax
0x140009cf5  movups  xmmword ptr [r14], xmm6
0x140009cf9  movups  xmmword ptr [r14+10h], xmm7
0x140009cfe  mov     [r12], rdi
0x140009d02  jmp     short loc_140009D09
0x140009d04  mov     eax, 0C000000Dh
0x140009d09  mov     rcx, [rbp+4Fh+var_60]
0x140009d0d  xor     rcx, rsp; StackCookie
0x140009d10  call    __security_check_cookie
0x140009d15  lea     r11, [rsp+120h+var_30]
0x140009d1d  mov     rbx, [r11+48h]
0x140009d21  movaps  xmm6, xmmword ptr [r11-10h]
0x140009d26  movaps  xmm7, xmmword ptr [r11-20h]
0x140009d2b  mov     rsp, r11
0x140009d2e  pop     r15
0x140009d30  pop     r14
0x140009d32  pop     r13
0x140009d34  pop     r12
0x140009d36  pop     rdi
0x140009d37  pop     rsi
0x140009d38  pop     rbp
0x140009d39  retn
```
