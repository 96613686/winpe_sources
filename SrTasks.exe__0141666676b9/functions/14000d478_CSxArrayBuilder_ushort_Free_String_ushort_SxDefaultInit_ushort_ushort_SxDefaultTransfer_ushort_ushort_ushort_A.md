# CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::Append(ushort * *)

- ea: `0x14000d478`
- end: `0x14000d564`
- name: `?Append@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@QEAAJPEAPEAG@Z`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x14000d688`

## callees

- `0x14000d478`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14000d528`
- `ole32!CoTaskMemFree` at `0x14000d528`
- `ole32!CoTaskMemRealloc` at `0x14000d506`
- `ole32!CoTaskMemRealloc` at `0x14000d506`

## pseudocode

```c
__int64 __fastcall CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::Append(
        __int64 a1,
        _QWORD *a2)
{
  int v4; // edi
  unsigned int v5; // eax
  unsigned int v6; // esi
  unsigned int v7; // ebx
  LPVOID v8; // rax

  if ( a2 )
  {
    v5 = *(_DWORD *)(a1 + 16);
    v6 = v5 + 1;
    if ( v5 + 1 < v5 )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      v4 = 0;
      if ( v6 > *(_DWORD *)(a1 + 20) )
      {
        v7 = 64;
        if ( v6 > 0x40 )
        {
          v7 = 256;
          if ( v6 > 0x100 )
          {
            v7 = 1024;
            if ( v6 > 0x400 )
            {
              v7 = 4096;
              if ( v6 > 0x1000 )
              {
                v7 = 0x4000;
                if ( v6 > 0x4000 )
                {
                  v7 = (v5 + 0x10000) & 0xFFFF0000;
                  if ( v7 < v6 )
                    v7 = v5 + 1;
                }
              }
            }
          }
        }
        if ( is_mul_ok(v7, 8u) )
        {
          v8 = CoTaskMemRealloc(*(LPVOID *)(a1 + 8), 8LL * v7);
          if ( v8 )
          {
            *(_QWORD *)(a1 + 8) = v8;
            *(_DWORD *)(a1 + 20) = v7;
          }
          else
          {
            v4 = -2147024882;
          }
        }
        else
        {
          v4 = -2147024362;
        }
      }
      CoTaskMemFree(0);
      if ( v4 >= 0 )
      {
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL * *(unsigned int *)(a1 + 16)) = *a2;
        *a2 = 0;
        *(_DWORD *)(a1 + 16) = v6;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000d478  mov     [rsp+arg_0], rbx
0x14000d47d  mov     [rsp+arg_10], rbp
0x14000d482  push    rsi
0x14000d483  push    rdi
0x14000d484  push    r14
0x14000d486  sub     rsp, 20h
0x14000d48a  mov     r14, rdx
0x14000d48d  mov     rbp, rcx
0x14000d490  test    rdx, rdx
0x14000d493  jnz     short loc_14000D49F
0x14000d495  mov     edi, 80070057h
0x14000d49a  jmp     loc_14000D54F
0x14000d49f  mov     eax, [rcx+10h]
0x14000d4a2  lea     esi, [rax+1]
0x14000d4a5  cmp     esi, eax
0x14000d4a7  jb      loc_14000D54A
0x14000d4ad  xor     edi, edi
0x14000d4af  cmp     esi, [rcx+14h]
0x14000d4b2  jbe     short loc_14000D526
0x14000d4b4  lea     ebx, [rdi+40h]
0x14000d4b7  cmp     esi, ebx
0x14000d4b9  jbe     short loc_14000D4F0
0x14000d4bb  mov     ebx, 100h
0x14000d4c0  cmp     esi, ebx
0x14000d4c2  jbe     short loc_14000D4F0
0x14000d4c4  mov     ebx, 400h
0x14000d4c9  cmp     esi, ebx
0x14000d4cb  jbe     short loc_14000D4F0
0x14000d4cd  mov     ebx, 1000h
0x14000d4d2  cmp     esi, ebx
0x14000d4d4  jbe     short loc_14000D4F0
0x14000d4d6  mov     ebx, 4000h
0x14000d4db  cmp     esi, ebx
0x14000d4dd  jbe     short loc_14000D4F0
0x14000d4df  lea     ebx, [rsi+0FFFFh]
0x14000d4e5  and     ebx, 0FFFF0000h
0x14000d4eb  cmp     ebx, esi
0x14000d4ed  cmovb   ebx, esi
0x14000d4f0  mov     ecx, ebx
0x14000d4f2  mov     eax, 8
0x14000d4f7  mul     rcx
0x14000d4fa  test    rdx, rdx
0x14000d4fd  jnz     short loc_14000D521
0x14000d4ff  mov     rcx, [rbp+8]; pv
0x14000d503  mov     rdx, rax; cb
0x14000d506  call    cs:__imp_CoTaskMemRealloc
0x14000d50c  test    rax, rax
0x14000d50f  jnz     short loc_14000D518
0x14000d511  mov     edi, 8007000Eh
0x14000d516  jmp     short loc_14000D526
0x14000d518  mov     [rbp+8], rax
0x14000d51c  mov     [rbp+14h], ebx
0x14000d51f  jmp     short loc_14000D526
0x14000d521  mov     edi, 80070216h
0x14000d526  xor     ecx, ecx; pv
0x14000d528  call    cs:__imp_CoTaskMemFree
0x14000d52e  test    edi, edi
0x14000d530  js      short loc_14000D54F
0x14000d532  mov     rax, [r14]
0x14000d535  mov     edx, [rbp+10h]
0x14000d538  mov     rcx, [rbp+8]
0x14000d53c  mov     [rcx+rdx*8], rax
0x14000d540  xor     eax, eax
0x14000d542  mov     [r14], rax
0x14000d545  mov     [rbp+10h], esi
0x14000d548  jmp     short loc_14000D54F
0x14000d54a  mov     edi, 80070216h
0x14000d54f  mov     rbx, [rsp+38h+arg_0]
0x14000d554  mov     eax, edi
0x14000d556  mov     rbp, [rsp+38h+arg_10]
0x14000d55b  add     rsp, 20h
0x14000d55f  pop     r14
0x14000d561  pop     rdi
0x14000d562  pop     rsi
0x14000d563  retn
```
