# StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)

- ea: `0x18000bdbc`
- end: `0x18000be64`
- name: `?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z`
- size: `168`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int16 **, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c728`

## callees

- `0x180005fb0`
- `0x18000bdbc`
- `0x18000c0c0`

## pseudocode

```c
__int64 __fastcall StringCchCopyExW(
        unsigned __int16 *a1,
        size_t a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int64 *a5)
{
  size_t v6; // rbx
  unsigned __int16 *v7; // rdi
  HRESULT v8; // edx
  wchar_t *v9; // rcx
  size_t v10; // r9
  HRESULT v11; // eax
  size_t v13; // [rsp+20h] [rbp-18h]
  size_t pcchNewDestLength; // [rsp+50h] [rbp+18h] BYREF

  pcchNewDestLength = (size_t)a3;
  v6 = a2;
  v7 = a1;
  v8 = StringExValidateDestW(a1, a2, (const size_t)a3, 0);
  if ( v8 < 0 )
  {
    if ( v6 )
      *v9 = 0;
  }
  else
  {
    if ( v6 )
    {
      pcchNewDestLength = v10;
      v11 = StringCopyWorkerW(v9, v6, &pcchNewDestLength, L"Microsoft Windows Network", v13);
      v8 = v11;
      v6 -= pcchNewDestLength;
      v7 += pcchNewDestLength;
      if ( v11 < 0 && v11 != -2147024774 )
        return (unsigned int)v8;
    }
    else
    {
      if ( !v9 )
        return (unsigned int)-2147024809;
      v8 = -2147024774;
    }
    if ( a4 )
      *a4 = v7;
    if ( a5 )
      *a5 = v6;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000bdbc  mov     [rsp+arg_0], rbx
0x18000bdc1  mov     [rsp+arg_8], rsi
0x18000bdc6  mov     [rsp+pcchNewDestLength], r8
0x18000bdcb  push    rdi
0x18000bdcc  sub     rsp, 30h
0x18000bdd0  mov     rsi, r9
0x18000bdd3  mov     rbx, rdx
0x18000bdd6  xor     r9d, r9d; dwFlags
0x18000bdd9  mov     rdi, rcx
0x18000bddc  call    StringExValidateDestW
0x18000bde1  mov     edx, eax
0x18000bde3  test    eax, eax
0x18000bde5  js      short loc_18000BE48
0x18000bde7  test    rbx, rbx
0x18000bdea  jnz     short loc_18000BDFF
0x18000bdec  test    rcx, rcx
0x18000bdef  jnz     short loc_18000BDF8
0x18000bdf1  mov     edx, 80070057h
0x18000bdf6  jmp     short loc_18000BE52
0x18000bdf8  mov     edx, 8007007Ah
0x18000bdfd  jmp     short loc_18000BE31
0x18000bdff  mov     [rsp+38h+pcchNewDestLength], r9
0x18000be04  lea     r8, [rsp+38h+pcchNewDestLength]; pcchNewDestLength
0x18000be09  lea     r9, aMicrosoftWindo; "Microsoft Windows Network"
0x18000be10  mov     rdx, rbx; cchDest
0x18000be13  call    StringCopyWorkerW
0x18000be18  mov     rcx, [rsp+38h+pcchNewDestLength]
0x18000be1d  mov     edx, eax
0x18000be1f  sub     rbx, rcx
0x18000be22  lea     rdi, [rdi+rcx*2]
0x18000be26  test    eax, eax
0x18000be28  jns     short loc_18000BE31
0x18000be2a  cmp     eax, 8007007Ah
0x18000be2f  jnz     short loc_18000BE52
0x18000be31  test    rsi, rsi
0x18000be34  jz      short loc_18000BE39
0x18000be36  mov     [rsi], rdi
0x18000be39  mov     rax, [rsp+38h+arg_20]
0x18000be3e  test    rax, rax
0x18000be41  jz      short loc_18000BE52
0x18000be43  mov     [rax], rbx
0x18000be46  jmp     short loc_18000BE52
0x18000be48  test    rbx, rbx
0x18000be4b  jz      short loc_18000BE52
0x18000be4d  xor     eax, eax
0x18000be4f  mov     [rcx], ax
0x18000be52  mov     rbx, [rsp+38h+arg_0]
0x18000be57  mov     eax, edx
0x18000be59  mov     rsi, [rsp+38h+arg_8]
0x18000be5e  add     rsp, 30h
0x18000be62  pop     rdi
0x18000be63  retn
```
