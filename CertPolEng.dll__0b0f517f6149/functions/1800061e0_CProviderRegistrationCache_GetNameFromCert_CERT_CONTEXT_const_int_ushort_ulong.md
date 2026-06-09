# CProviderRegistrationCache::GetNameFromCert(_CERT_CONTEXT const *,int,ushort * *,ulong *)

- ea: `0x1800061e0`
- end: `0x18000628e`
- name: `?GetNameFromCert@CProviderRegistrationCache@@QEAAKPEBU_CERT_CONTEXT@@HPEAPEAGPEAK@Z`
- size: `174`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, const struct _CERT_CONTEXT *, int, HLOCAL *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800157d4`
- `0x18001640c`

## callees

- `0x1800061e0`
- `0x1800062a0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006279`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006279`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::GetNameFromCert(
        CProviderRegistrationCache *this,
        const struct _CERT_CONTEXT *a2,
        int a3,
        HLOCAL *a4,
        unsigned int *a5)
{
  unsigned int *v5; // rsi
  unsigned int CertName; // eax
  unsigned int v8; // ebx
  unsigned int v9; // edx
  __int64 result; // rax
  HLOCAL hMem; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v12; // [rsp+60h] [rbp+8h] BYREF
  int v13; // [rsp+64h] [rbp+Ch]
  unsigned int v14; // [rsp+78h] [rbp+20h] BYREF

  v13 = HIDWORD(this);
  v5 = a5;
  *a4 = 0;
  hMem = 0;
  v12 = 0;
  v14 = 0;
  *v5 = 0;
  CertName = GetCertName(a2, a3, "2.5.4.3", (unsigned __int8 **)&hMem, &v12, &v14);
  v8 = CertName;
  if ( CertName != 14 )
  {
    if ( !CertName )
    {
      v9 = v12;
      if ( v12 > 2 )
      {
        result = 0;
        *a4 = hMem;
        *v5 = v9 >> 1;
        return result;
      }
    }
    v8 = 87;
  }
  if ( hMem )
    LocalFree(hMem);
  return v8;
}

```

## disassembly

```asm
0x1800061e0  mov     r11, rsp
0x1800061e3  mov     [r11+10h], rbx
0x1800061e7  mov     [r11+8], rcx
0x1800061eb  push    rbp
0x1800061ec  push    rsi
0x1800061ed  push    rdi
0x1800061ee  sub     rsp, 40h
0x1800061f2  mov     rsi, [rsp+58h+arg_20]
0x1800061fa  lea     rcx, [r11+20h]
0x1800061fe  xor     ebp, ebp
0x180006200  mov     [r11-30h], rcx
0x180006204  lea     rcx, [r11+8]
0x180006208  mov     [r9], rbp
0x18000620b  mov     eax, r8d
0x18000620e  mov     [r11-38h], rcx
0x180006212  mov     r10, rdx
0x180006215  mov     [r11-28h], rbp
0x180006219  mov     rdi, r9
0x18000621c  mov     [rsp+58h+arg_0], ebp
0x180006220  mov     rcx, r10; struct _CERT_CONTEXT *
0x180006223  mov     [rsp+58h+arg_18], ebp
0x180006227  lea     r9, [r11-28h]; unsigned __int8 **
0x18000622b  mov     [rsi], ebp
0x18000622d  lea     r8, a2543; "2.5.4.3"
0x180006234  mov     edx, eax; int
0x180006236  call    ?GetCertName@@YAKPEBU_CERT_CONTEXT@@HPEADPEAPEAEPEAK3@Z; GetCertName(_CERT_CONTEXT const *,int,char *,uchar * *,ulong *,ulong *)
0x18000623b  mov     ebx, eax
0x18000623d  cmp     eax, 0Eh
0x180006240  jz      short loc_18000626F
0x180006242  test    eax, eax
0x180006244  jnz     short loc_18000626A
0x180006246  mov     edx, [rsp+58h+arg_0]
0x18000624a  cmp     edx, 2
0x18000624d  jbe     short loc_18000626A
0x18000624f  mov     rcx, [rsp+58h+hMem]
0x180006254  mov     eax, ebp
0x180006256  shr     edx, 1
0x180006258  mov     [rdi], rcx
0x18000625b  mov     [rsi], edx
0x18000625d  mov     rbx, [rsp+58h+arg_8]
0x180006262  add     rsp, 40h
0x180006266  pop     rdi
0x180006267  pop     rsi
0x180006268  pop     rbp
0x180006269  retn
0x18000626a  mov     ebx, 57h ; 'W'
0x18000626f  mov     rcx, [rsp+58h+hMem]; hMem
0x180006274  test    rcx, rcx
0x180006277  jz      short loc_18000627F
0x180006279  call    cs:__imp_LocalFree
0x18000627f  mov     eax, ebx
0x180006281  mov     rbx, [rsp+58h+arg_8]
0x180006286  add     rsp, 40h
0x18000628a  pop     rdi
0x18000628b  pop     rsi
0x18000628c  pop     rbp
0x18000628d  retn
```
