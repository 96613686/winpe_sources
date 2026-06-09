# ATL::CSid::Sid(void)

- ea: `0x18001ecbc`
- end: `0x18001edfb`
- name: `?Sid@CSid@ATL@@QEBAPEBGXZ`
- size: `319`
- prototype: `const unsigned __int16 *__fastcall(ATL::CSid *__hidden this)`
- caller_count: `22`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017c0c`
- `0x1800191cc`
- `0x18001d580`
- `0x18001ee04`
- `0x180054da0`
- `0x1800567ac`
- `0x18005c0ec`
- `0x18005ccf8`
- `0x18006a280`
- `0x1800765f0`
- `0x1800769c0`
- `0x18009b1ac`
- `0x1800a4b18`
- `0x1800c0e0c`
- `0x1800c10a4`
- `0x1800c1bac`
- `0x1800c22c0`
- `0x1800c2ea0`
- `0x180109a40`
- `0x180109cd0`
- `0x180109e90`
- `0x18010ee3c`

## callees

- `0x180019738`
- `0x18001e75c`
- `0x18001e838`
- `0x18001ea58`
- `0x18001ecbc`
- `0x1800a98c0`
- `0x1800aa46a`
- `0x1800aa594`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001ed76`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001ed76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eda3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eda3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001ed00`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001ed00`

## pseudocode

```c
const unsigned __int16 *__fastcall ATL::CSid::Sid(ATL::CSid *this)
{
  const unsigned __int16 **v1; // rdi
  LPWSTR v2; // r14
  __int64 v3; // rbx
  const unsigned __int16 *v4; // rsi
  unsigned __int64 v5; // r15
  unsigned __int64 v6; // rdx
  unsigned __int16 *v7; // rcx
  __int64 v8; // rsi
  const unsigned __int16 *result; // rax
  LPWSTR StringSid; // [rsp+28h] [rbp-50h] BYREF

  try
  {
    v1 = (const unsigned __int16 **)((char *)this + 104);
    if ( !*(_DWORD *)(*((_QWORD *)this + 13) - 16LL) )
    {
      StringSid = 0;
      if ( ConvertSidToStringSidW((char *)this + 8, &StringSid) )
      {
        v2 = StringSid;
        if ( !StringSid )
          goto LABEL_20;
        v3 = -1;
        do
          ++v3;
        while ( StringSid[v3] );
        if ( (_DWORD)v3 )
        {
          v4 = *v1;
          v5 = *((unsigned int *)*v1 - 4);
          if ( (int)((*((_DWORD *)*v1 - 3) - v3) | (1 - *((_DWORD *)*v1 - 2))) < 0 )
            ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v1, (unsigned int)v3);
          v6 = v2 - v4;
          v7 = (unsigned __int16 *)*v1;
          v8 = (int)v3;
          if ( v6 <= v5 )
          {
            memmove_s(v7, 2LL * (int)v3, &v7[v6], 2LL * (int)v3);
          }
          else if ( v8 * 2 )
          {
            if ( v7 )
            {
              memcpy_0(v7, v2, 2LL * (int)v3);
            }
            else
            {
              *(_DWORD *)_o__errno(0) = 22;
              invalid_parameter_noinfo();
            }
          }
          if ( (int)v3 < 0 || (int)v3 > *((_DWORD *)*v1 - 3) )
            ATL::AtlThrowImpl(-2147024809);
          *((_DWORD *)*v1 - 4) = v3;
          (*v1)[v8] = 0;
        }
        else
        {
LABEL_20:
          ATL::CSimpleStringT<unsigned short,0>::Empty(v1);
        }
        LocalFree(StringSid);
      }
    }
    result = *v1;
  }
  catch ( ... )
  {
    ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 104);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18001ecbc  push    rbx
0x18001ecbe  push    rsi
0x18001ecbf  push    rdi
0x18001ecc0  push    r12
0x18001ecc2  push    r14
0x18001ecc4  push    r15
0x18001ecc6  sub     rsp, 48h
0x18001ecca  mov     rax, cs:__security_cookie
0x18001ecd1  xor     rax, rsp
0x18001ecd4  mov     [rsp+78h+var_48], rax
0x18001ecd9  mov     [rsp+78h+var_58], rcx
0x18001ecde  lea     rdi, [rcx+68h]
0x18001ece2  mov     rax, [rdi]
0x18001ece5  xor     r12d, r12d
0x18001ece8  cmp     [rax-10h], r12d
0x18001ecec  jnz     loc_18001EDA9
0x18001ecf2  mov     [rsp+78h+StringSid], r12
0x18001ecf7  add     rcx, 8; Sid
0x18001ecfb  lea     rdx, [rsp+78h+StringSid]; StringSid
0x18001ed00  call    cs:__imp_ConvertSidToStringSidW
0x18001ed06  test    eax, eax
0x18001ed08  jz      loc_18001EDA9
0x18001ed0e  mov     r14, [rsp+78h+StringSid]
0x18001ed13  test    r14, r14
0x18001ed16  jz      loc_18001EDD4
0x18001ed1c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001ed20  inc     rbx
0x18001ed23  cmp     [r14+rbx*2], r12w
0x18001ed28  jnz     short loc_18001ED20
0x18001ed2a  test    ebx, ebx
0x18001ed2c  jz      loc_18001EDD4
0x18001ed32  mov     rsi, [rdi]
0x18001ed35  mov     r15d, [rsi-10h]
0x18001ed39  mov     ecx, 1
0x18001ed3e  sub     ecx, [rsi-8]
0x18001ed41  mov     eax, [rsi-0Ch]
0x18001ed44  sub     eax, ebx
0x18001ed46  or      ecx, eax
0x18001ed48  jge     short loc_18001ED54
0x18001ed4a  mov     edx, ebx
0x18001ed4c  mov     rcx, rdi
0x18001ed4f  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18001ed54  mov     rdx, r14
0x18001ed57  sub     rdx, rsi
0x18001ed5a  sar     rdx, 1
0x18001ed5d  mov     rcx, [rdi]; void *
0x18001ed60  movsxd  rax, ebx
0x18001ed63  lea     rsi, [rax+rax]
0x18001ed67  cmp     rdx, r15
0x18001ed6a  jbe     short loc_18001EDDE
0x18001ed6c  test    rsi, rsi
0x18001ed6f  jz      short loc_18001ED87
0x18001ed71  test    rcx, rcx
0x18001ed74  jnz     short loc_18001EDC7
0x18001ed76  call    cs:__imp__o__errno
0x18001ed7c  mov     dword ptr [rax], 16h
0x18001ed82  call    _invalid_parameter_noinfo
0x18001ed87  test    ebx, ebx
0x18001ed89  js      short loc_18001EDEF
0x18001ed8b  mov     rax, [rdi]
0x18001ed8e  cmp     ebx, [rax-0Ch]
0x18001ed91  jg      short loc_18001EDEF
0x18001ed93  mov     [rax-10h], ebx
0x18001ed96  mov     rcx, [rdi]
0x18001ed99  mov     [rsi+rcx], r12w
0x18001ed9e  mov     rcx, [rsp+78h+StringSid]; hMem
0x18001eda3  call    cs:__imp_LocalFree
0x18001eda9  mov     rax, [rdi]
0x18001edac  mov     rcx, [rsp+78h+var_48]
0x18001edb1  xor     rcx, rsp; StackCookie
0x18001edb4  call    __security_check_cookie
0x18001edb9  add     rsp, 48h
0x18001edbd  pop     r15
0x18001edbf  pop     r14
0x18001edc1  pop     r12
0x18001edc3  pop     rdi
0x18001edc4  pop     rsi
0x18001edc5  pop     rbx
0x18001edc6  retn
0x18001edc7  mov     r8, rsi; Size
0x18001edca  mov     rdx, r14; Src
0x18001edcd  call    memcpy_0
0x18001edd2  jmp     short loc_18001ED87
0x18001edd4  mov     rcx, rdi
0x18001edd7  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18001eddc  jmp     short loc_18001ED9E
0x18001edde  lea     r8, [rcx+rdx*2]; Source
0x18001ede2  mov     r9, rsi; SourceSize
0x18001ede5  mov     rdx, rsi; DestinationSize
0x18001ede8  call    memmove_s
0x18001eded  jmp     short loc_18001ED87
0x18001edef  mov     ecx, 80070057h; int
0x18001edf4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
