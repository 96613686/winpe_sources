# Smb2ComputeValidateNegotiateInfoHash

- ea: `0x140095588`
- end: `0x140095741`
- name: `Smb2ComputeValidateNegotiateInfoHash`
- size: `441`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int16, __int64, __int64, ULONG Tag)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14006d82c`
- `0x140090240`

## callees

- `0x140095588`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400955fb`
- `ntoskrnl!ExAllocatePool2` at `0x1400955fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009570d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009570d`
- `srvnet!SmbCryptoHashCreate` at `0x1400955c0`
- `srvnet!SmbCryptoHashCreate` at `0x1400955c0`
- `srvnet!SmbCryptoHashGetOutputLength` at `0x1400955e2`
- `srvnet!SmbCryptoHashGetOutputLength` at `0x1400955e2`
- `srvnet!SmbCryptoHashUpdate` at `0x14009562a`
- `srvnet!SmbCryptoHashUpdate` at `0x14009564e`
- `srvnet!SmbCryptoHashUpdate` at `0x140095671`
- `srvnet!SmbCryptoHashUpdate` at `0x140095691`
- `srvnet!SmbCryptoHashUpdate` at `0x1400956b3`
- `srvnet!SmbCryptoHashUpdate` at `0x14009562a`
- `srvnet!SmbCryptoHashUpdate` at `0x14009564e`
- `srvnet!SmbCryptoHashUpdate` at `0x140095671`
- `srvnet!SmbCryptoHashUpdate` at `0x140095691`
- `srvnet!SmbCryptoHashUpdate` at `0x1400956b3`
- `srvnet!SmbCryptoHashFinish` at `0x1400956cf`
- `srvnet!SmbCryptoHashFinish` at `0x1400956cf`
- `srvnet!SmbCryptoHashDestroy` at `0x1400956f2`
- `srvnet!SmbCryptoHashDestroy` at `0x1400956f2`

## pseudocode

```c
__int64 __fastcall Smb2ComputeValidateNegotiateInfoHash(
        unsigned int a1,
        int a2,
        __int64 a3,
        __int16 a4,
        __int64 a5,
        unsigned __int16 a6,
        _QWORD *a7,
        _DWORD *a8,
        ULONG Tag)
{
  void *Pool2; // rdi
  int v11; // eax
  _DWORD *v12; // r14
  int v13; // ebx
  _QWORD *v14; // r15
  __int64 OutputLength; // rsi
  __int64 v17; // [rsp+20h] [rbp-10h] BYREF
  int v18; // [rsp+68h] [rbp+38h] BYREF
  __int16 v19; // [rsp+78h] [rbp+48h] BYREF

  v19 = a4;
  v18 = a2;
  v17 = 0;
  Pool2 = 0;
  v11 = SmbCryptoHashCreate(&v17, a1, 0);
  v12 = a8;
  v13 = v11;
  v14 = a7;
  if ( v11 >= 0 )
  {
    OutputLength = (unsigned int)SmbCryptoHashGetOutputLength(v17);
    Pool2 = (void *)ExAllocatePool2(258, OutputLength, Tag);
    if ( Pool2 )
    {
      v13 = SmbCryptoHashUpdate(v17, &Smb2SaltBuffer, 32);
      if ( v13 >= 0 )
      {
        v13 = SmbCryptoHashUpdate(v17, &v18, 4);
        if ( v13 >= 0 )
        {
          v13 = SmbCryptoHashUpdate(v17, a3, 16);
          if ( v13 >= 0 )
          {
            v13 = SmbCryptoHashUpdate(v17, &v19, 2);
            if ( v13 >= 0 )
            {
              v13 = SmbCryptoHashUpdate(v17, a5, 2 * (unsigned int)a6);
              if ( v13 >= 0 )
              {
                v13 = SmbCryptoHashFinish(v17, Pool2, (unsigned int)OutputLength);
                if ( v13 >= 0 )
                {
                  *v14 = Pool2;
                  v13 = 0;
                  *v12 = OutputLength;
                }
              }
            }
          }
        }
      }
    }
    else
    {
      v13 = -1073741670;
    }
  }
  if ( v17 )
    SmbCryptoHashDestroy();
  if ( v13 < 0 )
  {
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, Tag);
    *v14 = 0;
    *v12 = 0;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140095588  mov     rax, rsp
0x14009558b  mov     [rax+8], rbx
0x14009558f  mov     [rax+18h], rsi
0x140095593  mov     [rax+20h], r9w
0x140095598  mov     [rax+10h], edx
0x14009559b  push    rbp
0x14009559c  push    rdi
0x14009559d  push    r12
0x14009559f  push    r14
0x1400955a1  push    r15
0x1400955a3  mov     rbp, rsp
0x1400955a6  sub     rsp, 30h
0x1400955aa  mov     r12, r8
0x1400955ad  mov     [rbp+var_10], 0
0x1400955b5  mov     edx, ecx
0x1400955b7  xor     r8d, r8d
0x1400955ba  lea     rcx, [rbp+var_10]
0x1400955be  xor     edi, edi
0x1400955c0  call    cs:__imp_SmbCryptoHashCreate
0x1400955c7  nop     dword ptr [rax+rax+00h]
0x1400955cc  mov     r14, [rbp+arg_38]
0x1400955d0  mov     ebx, eax
0x1400955d2  mov     r15, [rbp+arg_30]
0x1400955d6  test    eax, eax
0x1400955d8  js      loc_1400956E9
0x1400955de  mov     rcx, [rbp+var_10]
0x1400955e2  call    cs:__imp_SmbCryptoHashGetOutputLength
0x1400955e9  nop     dword ptr [rax+rax+00h]
0x1400955ee  mov     r8d, [rbp+Tag]
0x1400955f2  mov     ecx, 102h
0x1400955f7  mov     edx, eax
0x1400955f9  mov     esi, eax
0x1400955fb  call    cs:__imp_ExAllocatePool2
0x140095602  nop     dword ptr [rax+rax+00h]
0x140095607  mov     rdi, rax
0x14009560a  test    rax, rax
0x14009560d  jnz     short loc_140095619
0x14009560f  mov     ebx, 0C000009Ah
0x140095614  jmp     loc_1400956E9
0x140095619  mov     rcx, [rbp+var_10]
0x14009561d  lea     rdx, Smb2SaltBuffer
0x140095624  mov     r8d, 20h ; ' '
0x14009562a  call    cs:__imp_SmbCryptoHashUpdate
0x140095631  nop     dword ptr [rax+rax+00h]
0x140095636  mov     ebx, eax
0x140095638  test    eax, eax
0x14009563a  js      loc_1400956E9
0x140095640  mov     rcx, [rbp+var_10]
0x140095644  lea     rdx, [rbp+arg_8]
0x140095648  mov     r8d, 4
0x14009564e  call    cs:__imp_SmbCryptoHashUpdate
0x140095655  nop     dword ptr [rax+rax+00h]
0x14009565a  mov     ebx, eax
0x14009565c  test    eax, eax
0x14009565e  js      loc_1400956E9
0x140095664  mov     rcx, [rbp+var_10]
0x140095668  mov     r8d, 10h
0x14009566e  mov     rdx, r12
0x140095671  call    cs:__imp_SmbCryptoHashUpdate
0x140095678  nop     dword ptr [rax+rax+00h]
0x14009567d  mov     ebx, eax
0x14009567f  test    eax, eax
0x140095681  js      short loc_1400956E9
0x140095683  mov     rcx, [rbp+var_10]
0x140095687  lea     rdx, [rbp+arg_18]
0x14009568b  mov     r8d, 2
0x140095691  call    cs:__imp_SmbCryptoHashUpdate
0x140095698  nop     dword ptr [rax+rax+00h]
0x14009569d  mov     ebx, eax
0x14009569f  test    eax, eax
0x1400956a1  js      short loc_1400956E9
0x1400956a3  movzx   r8d, [rbp+arg_28]
0x1400956a8  mov     rdx, [rbp+arg_20]
0x1400956ac  add     r8d, r8d
0x1400956af  mov     rcx, [rbp+var_10]
0x1400956b3  call    cs:__imp_SmbCryptoHashUpdate
0x1400956ba  nop     dword ptr [rax+rax+00h]
0x1400956bf  mov     ebx, eax
0x1400956c1  test    eax, eax
0x1400956c3  js      short loc_1400956E9
0x1400956c5  mov     rcx, [rbp+var_10]
0x1400956c9  mov     r8d, esi
0x1400956cc  mov     rdx, rdi
0x1400956cf  call    cs:__imp_SmbCryptoHashFinish
0x1400956d6  nop     dword ptr [rax+rax+00h]
0x1400956db  mov     ebx, eax
0x1400956dd  test    eax, eax
0x1400956df  js      short loc_1400956E9
0x1400956e1  mov     [r15], rdi
0x1400956e4  xor     ebx, ebx
0x1400956e6  mov     [r14], esi
0x1400956e9  mov     rcx, [rbp+var_10]
0x1400956ed  test    rcx, rcx
0x1400956f0  jz      short loc_1400956FE
0x1400956f2  call    cs:__imp_SmbCryptoHashDestroy
0x1400956f9  nop     dword ptr [rax+rax+00h]
0x1400956fe  test    ebx, ebx
0x140095700  jns     short loc_140095727
0x140095702  test    rdi, rdi
0x140095705  jz      short loc_140095719
0x140095707  mov     edx, [rbp+Tag]; Tag
0x14009570a  mov     rcx, rdi; P
0x14009570d  call    cs:__imp_ExFreePoolWithTag
0x140095714  nop     dword ptr [rax+rax+00h]
0x140095719  mov     qword ptr [r15], 0
0x140095720  mov     dword ptr [r14], 0
0x140095727  mov     rsi, [rsp+30h+arg_10]
0x14009572c  mov     eax, ebx
0x14009572e  mov     rbx, [rsp+30h+arg_0]
0x140095733  add     rsp, 30h
0x140095737  pop     r15
0x140095739  pop     r14
0x14009573b  pop     r12
0x14009573d  pop     rdi
0x14009573e  pop     rbp
0x14009573f  retn
```
