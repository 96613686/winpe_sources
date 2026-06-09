# RoutePolicyCallout::QueryConnectionCache(RoutePolicyCallout::CONNECTION_CACHE_LIST * const,ulong,ulong *)

- ea: `0x140005b60`
- end: `0x140005ef5`
- name: `?QueryConnectionCache@RoutePolicyCallout@@YAJQEAUCONNECTION_CACHE_LIST@1@KPEAK@Z`
- size: `917`
- prototype: `__int64 __fastcall(RoutePolicyCallout *__hidden this, struct RoutePolicyCallout::CONNECTION_CACHE_LIST *const, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140008798`

## callees

- `0x1400012f0`
- `0x140005b60`
- `0x140007d28`
- `0x140007d7c`
- `0x14000a680`
- `0x14000a780`
- `0x14000aa80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140005c5d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005d62`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005c5d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005d62`

## pseudocode

```c
__int64 __fastcall RoutePolicyCallout::QueryConnectionCache(
        RoutePolicyCallout *this,
        struct RoutePolicyCallout::CONNECTION_CACHE_LIST *const a2,
        unsigned int *a3,
        unsigned int *a4)
{
  unsigned int v4; // r13d
  unsigned int *v6; // rdi
  unsigned int v7; // esi
  _QWORD **v8; // rax
  _QWORD *v9; // r14
  __int64 *i; // rdi
  int v11; // eax
  const WCHAR *v12; // rdx
  _OWORD *v13; // rcx
  wchar_t *Buffer; // rax
  const WCHAR *v15; // rdx
  _OWORD *v16; // rcx
  wchar_t *v17; // rax
  unsigned int v18; // ebx
  int v20; // [rsp+30h] [rbp-59h] BYREF
  unsigned int *v21; // [rsp+38h] [rbp-51h] BYREF
  __int128 v22; // [rsp+40h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+60h] [rbp-29h] BYREF
  unsigned int **v25; // [rsp+80h] [rbp-9h]
  __int64 v26; // [rsp+88h] [rbp-1h]
  int *v27; // [rsp+90h] [rbp+7h]
  __int64 v28; // [rsp+98h] [rbp+Fh]

  v4 = (unsigned int)a2;
  v21 = a3;
  v6 = a3;
  AcquireSpinLock(&v22, (char *)RoutePolicyCallout::g_pCalloutContext + 40);
  v7 = 8;
  v8 = (_QWORD **)((char *)RoutePolicyCallout::g_pCalloutContext + 48);
  *v6 = 8;
  *(_DWORD *)this = 0;
  v9 = *v8;
  if ( *v8 != v8 )
  {
    do
    {
      for ( i = (__int64 *)v9[4]; i != v9 + 4; i = (__int64 *)*i )
      {
        ++*(_DWORD *)this;
        v7 += 552;
        if ( v4 >= v7 )
        {
          memset((char *)this + 8, 0, 0x228u);
          *((_QWORD *)this + 1) = v9[2];
          *((_QWORD *)this + 2) = i[6];
          *((_WORD *)this + 12) = *((_WORD *)i + 28);
          *(_OWORD *)((char *)this + 28) = *((_OWORD *)i + 4);
          *(_OWORD *)((char *)this + 40) = *(_OWORD *)((char *)i + 76);
          *(_OWORD *)((char *)this + 56) = *(_OWORD *)((char *)i + 92);
          *(_OWORD *)((char *)this + 68) = *(_OWORD *)(i + 13);
          *((_BYTE *)this + 84) = *((_BYTE *)i + 130);
          v11 = *((_DWORD *)i + 4);
          *((_DWORD *)this + 22) = v11;
          if ( (v11 & 0x800) != 0 )
          {
            v12 = (const WCHAR *)i[3];
            DestinationString = 0;
            RtlInitUnicodeString(&DestinationString, v12);
            v13 = (_OWORD *)((char *)this + 92);
            if ( DestinationString.MaximumLength >= 0x100u )
            {
              Buffer = DestinationString.Buffer;
              *v13 = *(_OWORD *)DestinationString.Buffer;
              *(_OWORD *)((char *)this + 108) = *((_OWORD *)Buffer + 1);
              *(_OWORD *)((char *)this + 124) = *((_OWORD *)Buffer + 2);
              *(_OWORD *)((char *)this + 140) = *((_OWORD *)Buffer + 3);
              *(_OWORD *)((char *)this + 156) = *((_OWORD *)Buffer + 4);
              *(_OWORD *)((char *)this + 172) = *((_OWORD *)Buffer + 5);
              *(_OWORD *)((char *)this + 188) = *((_OWORD *)Buffer + 6);
              *(_OWORD *)((char *)this + 204) = *((_OWORD *)Buffer + 7);
              *(_OWORD *)((char *)this + 220) = *((_OWORD *)Buffer + 8);
              *(_OWORD *)((char *)this + 236) = *((_OWORD *)Buffer + 9);
              *(_OWORD *)((char *)this + 252) = *((_OWORD *)Buffer + 10);
              *(_OWORD *)((char *)this + 268) = *((_OWORD *)Buffer + 11);
              *(_OWORD *)((char *)this + 284) = *((_OWORD *)Buffer + 12);
              *(_OWORD *)((char *)this + 300) = *((_OWORD *)Buffer + 13);
              *(_OWORD *)((char *)this + 316) = *((_OWORD *)Buffer + 14);
              *(_OWORD *)((char *)this + 330) = *(_OWORD *)(Buffer + 119);
              *((_WORD *)this + 173) = 0;
            }
            else
            {
              memmove(v13, DestinationString.Buffer, DestinationString.MaximumLength);
            }
          }
          if ( (*((_DWORD *)this + 22) & 0x1000) != 0 )
          {
            v15 = (const WCHAR *)i[4];
            DestinationString = 0;
            RtlInitUnicodeString(&DestinationString, v15);
            v16 = (_OWORD *)((char *)this + 348);
            if ( DestinationString.MaximumLength >= 0xCAu )
            {
              v17 = DestinationString.Buffer;
              *v16 = *(_OWORD *)DestinationString.Buffer;
              *(_OWORD *)((char *)this + 364) = *((_OWORD *)v17 + 1);
              *(_OWORD *)((char *)this + 380) = *((_OWORD *)v17 + 2);
              *(_OWORD *)((char *)this + 396) = *((_OWORD *)v17 + 3);
              *(_OWORD *)((char *)this + 412) = *((_OWORD *)v17 + 4);
              *(_OWORD *)((char *)this + 428) = *((_OWORD *)v17 + 5);
              *(_OWORD *)((char *)this + 444) = *((_OWORD *)v17 + 6);
              *(_OWORD *)((char *)this + 460) = *((_OWORD *)v17 + 7);
              *(_OWORD *)((char *)this + 476) = *((_OWORD *)v17 + 8);
              *(_OWORD *)((char *)this + 492) = *((_OWORD *)v17 + 9);
              *(_OWORD *)((char *)this + 508) = *((_OWORD *)v17 + 10);
              *(_OWORD *)((char *)this + 524) = *((_OWORD *)v17 + 11);
              *(_QWORD *)((char *)this + 540) = *((_QWORD *)v17 + 24);
              *((_WORD *)this + 274) = 0;
            }
            else
            {
              memmove(v16, DestinationString.Buffer, DestinationString.MaximumLength);
            }
          }
        }
      }
      v9 = (_QWORD *)*v9;
    }
    while ( v9 != (_QWORD *)((char *)RoutePolicyCallout::g_pCalloutContext + 48) );
    v6 = v21;
  }
  if ( v4 >= v7 )
  {
    v18 = 0;
    *v6 = v7;
  }
  else
  {
    *(_DWORD *)this = v7;
    if ( (unsigned int)dword_140012050 > 4 )
    {
      v20 = *(_DWORD *)this;
      v28 = 4;
      v27 = &v20;
      v26 = 4;
      v25 = &v21;
      LODWORD(v21) = v7;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, (unsigned __int8 *)&word_140010212, 0, 0, 4u, &v24);
    }
    v18 = -2147483643;
  }
  if ( (_QWORD)v22 )
    SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v22);
  return v18;
}

```

## disassembly

```asm
0x140005b60  mov     [rsp-8+arg_8], rbx
0x140005b65  push    rbp
0x140005b66  push    rsi
0x140005b67  push    rdi
0x140005b68  push    r12
0x140005b6a  push    r13
0x140005b6c  push    r14
0x140005b6e  push    r15
0x140005b70  lea     rbp, [rsp-27h]
0x140005b75  sub     rsp, 0B0h
0x140005b7c  mov     rax, cs:__security_cookie
0x140005b83  xor     rax, rsp
0x140005b86  mov     [rbp+57h+var_40], rax
0x140005b8a  mov     r13d, edx
0x140005b8d  mov     [rbp+57h+var_A8], r8
0x140005b91  mov     rdx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140005b98  mov     rbx, rcx
0x140005b9b  add     rdx, 28h ; '('
0x140005b9f  lea     rcx, [rbp+57h+var_A0]
0x140005ba3  mov     rdi, r8
0x140005ba6  call    ?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z; AcquireSpinLock(unsigned __int64 *)
0x140005bab  mov     rax, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140005bb2  mov     esi, 8
0x140005bb7  add     rax, 30h ; '0'
0x140005bbb  mov     [rdi], esi
0x140005bbd  mov     dword ptr [rbx], 0
0x140005bc3  mov     r14, [rax]
0x140005bc6  cmp     r14, rax
0x140005bc9  jz      loc_140005E4B
0x140005bcf  lea     r15, [r14+20h]
0x140005bd3  mov     rdi, [r15]
0x140005bd6  jmp     loc_140005E27
0x140005bdb  inc     dword ptr [rbx]
0x140005bdd  add     esi, 228h
0x140005be3  cmp     r13d, esi
0x140005be6  jb      loc_140005E24
0x140005bec  xor     edx, edx; Val
0x140005bee  lea     rcx, [rbx+8]; void *
0x140005bf2  mov     r8d, 228h; Size
0x140005bf8  call    memset
0x140005bfd  mov     rax, [r14+10h]
0x140005c01  mov     [rbx+8], rax
0x140005c05  mov     rax, [rdi+30h]
0x140005c09  mov     [rbx+10h], rax
0x140005c0d  movzx   eax, word ptr [rdi+38h]
0x140005c11  mov     [rbx+18h], ax
0x140005c15  movups  xmm0, xmmword ptr [rdi+40h]
0x140005c19  movups  xmmword ptr [rbx+1Ch], xmm0
0x140005c1d  movups  xmm1, xmmword ptr [rdi+4Ch]
0x140005c21  movups  xmmword ptr [rbx+28h], xmm1
0x140005c25  movups  xmm0, xmmword ptr [rdi+5Ch]
0x140005c29  movups  xmmword ptr [rbx+38h], xmm0
0x140005c2d  movups  xmm1, xmmword ptr [rdi+68h]
0x140005c31  movups  xmmword ptr [rbx+44h], xmm1
0x140005c35  mov     al, [rdi+82h]
0x140005c3b  mov     [rbx+54h], al
0x140005c3e  mov     eax, [rdi+10h]
0x140005c41  mov     [rbx+58h], eax
0x140005c44  bt      eax, 0Bh
0x140005c48  jnb     loc_140005D46
0x140005c4e  mov     rdx, [rdi+18h]; SourceString
0x140005c52  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140005c56  xorps   xmm0, xmm0
0x140005c59  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140005c5d  call    cs:__imp_RtlInitUnicodeString
0x140005c64  nop     dword ptr [rax+rax+00h]
0x140005c69  mov     eax, 100h
0x140005c6e  lea     rcx, [rbx+5Ch]; void *
0x140005c72  cmp     [rbp+57h+DestinationString.MaximumLength], ax
0x140005c76  jnb     short loc_140005C8B
0x140005c78  movzx   r8d, [rbp+57h+DestinationString.MaximumLength]; Size
0x140005c7d  mov     rdx, [rbp+57h+DestinationString.Buffer]; Src
0x140005c81  call    memmove
0x140005c86  jmp     loc_140005D46
0x140005c8b  mov     rax, [rbp+57h+DestinationString.Buffer]
0x140005c8f  movups  xmm0, xmmword ptr [rax]
0x140005c92  movups  xmmword ptr [rcx], xmm0
0x140005c95  movups  xmm1, xmmword ptr [rax+10h]
0x140005c99  movups  xmmword ptr [rcx+10h], xmm1
0x140005c9d  movups  xmm0, xmmword ptr [rax+20h]
0x140005ca1  movups  xmmword ptr [rcx+20h], xmm0
0x140005ca5  movups  xmm1, xmmword ptr [rax+30h]
0x140005ca9  movups  xmmword ptr [rcx+30h], xmm1
0x140005cad  movups  xmm0, xmmword ptr [rax+40h]
0x140005cb1  movups  xmmword ptr [rcx+40h], xmm0
0x140005cb5  movups  xmm1, xmmword ptr [rax+50h]
0x140005cb9  movups  xmmword ptr [rcx+50h], xmm1
0x140005cbd  movups  xmm0, xmmword ptr [rax+60h]
0x140005cc1  movups  xmmword ptr [rcx+60h], xmm0
0x140005cc5  movups  xmm1, xmmword ptr [rax+70h]
0x140005cc9  movups  xmmword ptr [rcx+70h], xmm1
0x140005ccd  movups  xmm0, xmmword ptr [rax+80h]
0x140005cd4  movups  xmmword ptr [rcx+80h], xmm0
0x140005cdb  movups  xmm1, xmmword ptr [rax+90h]
0x140005ce2  movups  xmmword ptr [rcx+90h], xmm1
0x140005ce9  movups  xmm0, xmmword ptr [rax+0A0h]
0x140005cf0  movups  xmmword ptr [rcx+0A0h], xmm0
0x140005cf7  movups  xmm1, xmmword ptr [rax+0B0h]
0x140005cfe  movups  xmmword ptr [rcx+0B0h], xmm1
0x140005d05  movups  xmm0, xmmword ptr [rax+0C0h]
0x140005d0c  movups  xmmword ptr [rcx+0C0h], xmm0
0x140005d13  movups  xmm1, xmmword ptr [rax+0D0h]
0x140005d1a  movups  xmmword ptr [rcx+0D0h], xmm1
0x140005d21  movups  xmm0, xmmword ptr [rax+0E0h]
0x140005d28  movups  xmmword ptr [rcx+0E0h], xmm0
0x140005d2f  movups  xmm1, xmmword ptr [rax+0EEh]
0x140005d36  xor     eax, eax
0x140005d38  movups  xmmword ptr [rcx+0EEh], xmm1
0x140005d3f  mov     [rbx+15Ah], ax
0x140005d46  test    dword ptr [rbx+58h], 1000h
0x140005d4d  jz      loc_140005E24
0x140005d53  mov     rdx, [rdi+20h]; SourceString
0x140005d57  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140005d5b  xorps   xmm0, xmm0
0x140005d5e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140005d62  call    cs:__imp_RtlInitUnicodeString
0x140005d69  nop     dword ptr [rax+rax+00h]
0x140005d6e  mov     eax, 0CAh
0x140005d73  lea     rcx, [rbx+15Ch]; void *
0x140005d7a  cmp     [rbp+57h+DestinationString.MaximumLength], ax
0x140005d7e  jnb     short loc_140005D93
0x140005d80  movzx   r8d, [rbp+57h+DestinationString.MaximumLength]; Size
0x140005d85  mov     rdx, [rbp+57h+DestinationString.Buffer]; Src
0x140005d89  call    memmove
0x140005d8e  jmp     loc_140005E24
0x140005d93  mov     rax, [rbp+57h+DestinationString.Buffer]
0x140005d97  movups  xmm0, xmmword ptr [rax]
0x140005d9a  movups  xmmword ptr [rcx], xmm0
0x140005d9d  movups  xmm1, xmmword ptr [rax+10h]
0x140005da1  movups  xmmword ptr [rcx+10h], xmm1
0x140005da5  movups  xmm0, xmmword ptr [rax+20h]
0x140005da9  movups  xmmword ptr [rcx+20h], xmm0
0x140005dad  movups  xmm1, xmmword ptr [rax+30h]
0x140005db1  movups  xmmword ptr [rcx+30h], xmm1
0x140005db5  movups  xmm0, xmmword ptr [rax+40h]
0x140005db9  movups  xmmword ptr [rcx+40h], xmm0
0x140005dbd  movups  xmm1, xmmword ptr [rax+50h]
0x140005dc1  movups  xmmword ptr [rcx+50h], xmm1
0x140005dc5  movups  xmm0, xmmword ptr [rax+60h]
0x140005dc9  movups  xmmword ptr [rcx+60h], xmm0
0x140005dcd  movups  xmm1, xmmword ptr [rax+70h]
0x140005dd1  movups  xmmword ptr [rcx+70h], xmm1
0x140005dd5  movups  xmm0, xmmword ptr [rax+80h]
0x140005ddc  movups  xmmword ptr [rcx+80h], xmm0
0x140005de3  movups  xmm1, xmmword ptr [rax+90h]
0x140005dea  movups  xmmword ptr [rcx+90h], xmm1
0x140005df1  movups  xmm0, xmmword ptr [rax+0A0h]
0x140005df8  movups  xmmword ptr [rcx+0A0h], xmm0
0x140005dff  movups  xmm1, xmmword ptr [rax+0B0h]
0x140005e06  movups  xmmword ptr [rcx+0B0h], xmm1
0x140005e0d  mov     rax, [rax+0C0h]
0x140005e14  mov     [rcx+0C0h], rax
0x140005e1b  xor     eax, eax
0x140005e1d  mov     [rbx+224h], ax
0x140005e24  mov     rdi, [rdi]
0x140005e27  cmp     rdi, r15
0x140005e2a  jnz     loc_140005BDB
0x140005e30  mov     rax, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140005e37  mov     r14, [r14]
0x140005e3a  add     rax, 30h ; '0'
0x140005e3e  cmp     r14, rax
0x140005e41  jnz     loc_140005BCF
0x140005e47  mov     rdi, [rbp+57h+var_A8]
0x140005e4b  cmp     r13d, esi
0x140005e4e  jnb     short loc_140005EAE
0x140005e50  mov     [rbx], esi
0x140005e52  mov     ecx, 4
0x140005e57  mov     eax, cs:dword_140012050
0x140005e5d  cmp     eax, ecx
0x140005e5f  jbe     short loc_140005EA7
0x140005e61  mov     eax, [rbx]
0x140005e63  lea     rdx, word_140010212; int
0x140005e6a  mov     [rbp+57h+var_B0], eax
0x140005e6d  xor     r9d, r9d; int
0x140005e70  lea     rax, [rbp+57h+var_B0]
0x140005e74  mov     [rbp+57h+var_48], rcx
0x140005e78  mov     [rbp+57h+var_50], rax
0x140005e7c  xor     r8d, r8d; int
0x140005e7f  lea     rax, [rbp+57h+var_A8]
0x140005e83  mov     [rbp+57h+var_58], rcx
0x140005e87  mov     [rbp+57h+var_60], rax
0x140005e8b  lea     rax, [rbp+57h+var_80]
0x140005e8f  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x140005e94  mov     [rsp+0E0h+var_C0], ecx; ULONG
0x140005e98  lea     rcx, dword_140012050; int
0x140005e9f  mov     dword ptr [rbp+57h+var_A8], esi
0x140005ea2  call    _tlgWriteTransfer_EtwWriteTransfer
0x140005ea7  mov     ebx, 80000005h
0x140005eac  jmp     short loc_140005EB2
0x140005eae  xor     ebx, ebx
0x140005eb0  mov     [rdi], esi
0x140005eb2  cmp     qword ptr [rbp+57h+var_A0], 0
0x140005eb7  jz      short loc_140005ECB
0x140005eb9  movaps  xmm0, [rbp+57h+var_A0]
0x140005ebd  lea     rcx, [rbp+57h+var_A0]; struct SpinLockAndSavedIrql *
0x140005ec1  movdqa  [rbp+57h+var_A0], xmm0
0x140005ec6  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140005ecb  mov     eax, ebx
0x140005ecd  mov     rcx, [rbp+57h+var_40]
0x140005ed1  xor     rcx, rsp; StackCookie
0x140005ed4  call    __security_check_cookie
0x140005ed9  mov     rbx, [rsp+0E0h+arg_8]
0x140005ee1  add     rsp, 0B0h
0x140005ee8  pop     r15
0x140005eea  pop     r14
0x140005eec  pop     r13
0x140005eee  pop     r12
0x140005ef0  pop     rdi
0x140005ef1  pop     rsi
0x140005ef2  pop     rbp
0x140005ef3  retn
```
