# CModelDownloadComponent::ValidateModelCurrentVersion(ushort const *,ushort *)

- ea: `0x1400127e4`
- end: `0x140012990`
- name: `?ValidateModelCurrentVersion@CModelDownloadComponent@@CAJPEBGPEAG@Z`
- size: `428`
- prototype: `__int64 __fastcall(wchar_t *FileName, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000d5a4`

## callees

- `0x140002600`
- `0x1400030dc`
- `0x1400127e4`
- `0x140012998`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x140012855`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x140012855`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x1400128b4`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x1400128b4`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x140012888`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1400128ee`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x140012917`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x14001294f`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x140012963`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x140012888`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1400128ee`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x140012917`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x14001294f`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x140012963`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x140012872`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x140012872`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14001293f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14001293f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140012902`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140012902`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::ValidateModelCurrentVersion(wchar_t *FileName, unsigned __int16 *a2)
{
  int v5; // ebx
  wchar_t *v6; // rax
  FILE *Stream; // [rsp+20h] [rbp-E0h] BYREF
  struct _stat64i32 Stat; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v10; // [rsp+270h] [rbp+170h]

  memset_0(Buffer, 0, 0x218u);
  if ( !FileName || !*FileName || !a2 )
    return 2147942487LL;
  Stream = 0;
  if ( _wfopen_s(&Stream, FileName, L"rb") || fread(Buffer, 0x218u, 1u, Stream) != 1 )
  {
    if ( Stream )
      fclose(Stream);
    return 2147942405LL;
  }
  memset(&Stat, 0, sizeof(Stat));
  if ( _wstat64i32(Buffer, &Stat) || Stat.st_mtime != v10 )
  {
    if ( Stream )
      fclose(Stream);
    return 2147942487LL;
  }
  v5 = CModelDownloadComponent::ValidateModelFilesList(Buffer);
  if ( v5 >= 0 )
  {
    v6 = wcsrchr(Buffer, 0x5Cu);
    if ( v6 )
    {
      _o_wcsncpy_s(a2, 260, Buffer, (int)(v6 - Buffer));
      if ( Stream )
        fclose(Stream);
      return 0;
    }
    else
    {
      if ( Stream )
        fclose(Stream);
      return 2148270082LL;
    }
  }
  else
  {
    if ( Stream )
      fclose(Stream);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x1400127e4  mov     [rsp-8+arg_10], rbx
0x1400127e9  push    rbp
0x1400127ea  push    rsi
0x1400127eb  push    rdi
0x1400127ec  lea     rbp, [rsp-190h]
0x1400127f4  sub     rsp, 290h
0x1400127fb  mov     rax, cs:__security_cookie
0x140012802  xor     rax, rsp
0x140012805  mov     [rbp+1A0h+var_20], rax
0x14001280c  mov     rdi, rdx
0x14001280f  mov     rbx, rcx
0x140012812  xor     edx, edx; Val
0x140012814  lea     rcx, [rsp+2A0h+Buffer]; void *
0x140012819  mov     r8d, 218h; Size
0x14001281f  call    memset_0
0x140012824  xor     esi, esi
0x140012826  test    rbx, rbx
0x140012829  jz      loc_140012969
0x14001282f  cmp     [rbx], si
0x140012832  jz      loc_140012969
0x140012838  test    rdi, rdi
0x14001283b  jz      loc_140012969
0x140012841  lea     r8, aRb; "rb"
0x140012848  mov     [rsp+2A0h+Stream], rsi
0x14001284d  mov     rdx, rbx; FileName
0x140012850  lea     rcx, [rsp+2A0h+Stream]; Stream
0x140012855  call    cs:__imp__wfopen_s
0x14001285b  test    eax, eax
0x14001285d  jnz     short loc_14001287E
0x14001285f  mov     r9, [rsp+2A0h+Stream]; Stream
0x140012864  lea     r8d, [rsi+1]; ElementCount
0x140012868  mov     edx, 218h; ElementSize
0x14001286d  lea     rcx, [rsp+2A0h+Buffer]; Buffer
0x140012872  call    cs:__imp_fread
0x140012878  cmp     rax, 1
0x14001287c  jz      short loc_140012898
0x14001287e  mov     rcx, [rsp+2A0h+Stream]; Stream
0x140012883  test    rcx, rcx
0x140012886  jz      short loc_14001288E
0x140012888  call    cs:__imp_fclose
0x14001288e  mov     eax, 80070005h
0x140012893  jmp     loc_14001296E
0x140012898  xorps   xmm0, xmm0
0x14001289b  lea     rdx, [rsp+2A0h+Stat]; Stat
0x1400128a0  lea     rcx, [rsp+2A0h+Buffer]; FileName
0x1400128a5  movups  xmmword ptr [rsp+2A0h+Stat.st_dev], xmm0
0x1400128aa  movups  xmmword ptr [rsp+2A0h+Stat.st_rdev], xmm0
0x1400128af  movups  xmmword ptr [rsp+2A0h+Stat.st_mtime], xmm0
0x1400128b4  call    cs:__imp__wstat64i32
0x1400128ba  test    eax, eax
0x1400128bc  jnz     loc_140012959
0x1400128c2  mov     rax, [rbp+1A0h+var_30]
0x1400128c9  cmp     [rsp+2A0h+Stat.st_mtime], rax
0x1400128ce  jnz     loc_140012959
0x1400128d4  lea     rcx, [rsp+2A0h+Buffer]; FileName
0x1400128d9  call    ?ValidateModelFilesList@CModelDownloadComponent@@CAJPEBG@Z; CModelDownloadComponent::ValidateModelFilesList(ushort const *)
0x1400128de  mov     ebx, eax
0x1400128e0  test    eax, eax
0x1400128e2  jns     short loc_1400128F8
0x1400128e4  mov     rcx, [rsp+2A0h+Stream]; Stream
0x1400128e9  test    rcx, rcx
0x1400128ec  jz      short loc_1400128F4
0x1400128ee  call    cs:__imp_fclose
0x1400128f4  mov     eax, ebx
0x1400128f6  jmp     short loc_14001296E
0x1400128f8  mov     edx, 5Ch ; '\'; Ch
0x1400128fd  lea     rcx, [rsp+2A0h+Buffer]; Str
0x140012902  call    cs:__imp_wcsrchr
0x140012908  test    rax, rax
0x14001290b  jnz     short loc_140012924
0x14001290d  mov     rcx, [rsp+2A0h+Stream]; Stream
0x140012912  test    rcx, rcx
0x140012915  jz      short loc_14001291D
0x140012917  call    cs:__imp_fclose
0x14001291d  mov     eax, 800C0002h
0x140012922  jmp     short loc_14001296E
0x140012924  lea     rcx, [rsp+2A0h+Buffer]
0x140012929  mov     edx, 104h
0x14001292e  sub     rax, rcx
0x140012931  lea     r8, [rsp+2A0h+Buffer]
0x140012936  sar     rax, 1
0x140012939  mov     rcx, rdi
0x14001293c  movsxd  r9, eax
0x14001293f  call    cs:__imp__o_wcsncpy_s
0x140012945  mov     rcx, [rsp+2A0h+Stream]; Stream
0x14001294a  test    rcx, rcx
0x14001294d  jz      short loc_140012955
0x14001294f  call    cs:__imp_fclose
0x140012955  xor     eax, eax
0x140012957  jmp     short loc_14001296E
0x140012959  mov     rcx, [rsp+2A0h+Stream]; Stream
0x14001295e  test    rcx, rcx
0x140012961  jz      short loc_140012969
0x140012963  call    cs:__imp_fclose
0x140012969  mov     eax, 80070057h
0x14001296e  mov     rcx, [rbp+1A0h+var_20]
0x140012975  xor     rcx, rsp; StackCookie
0x140012978  call    __security_check_cookie
0x14001297d  mov     rbx, [rsp+2A0h+arg_10]
0x140012985  add     rsp, 290h
0x14001298c  pop     rdi
0x14001298d  pop     rsi
0x14001298e  pop     rbp
0x14001298f  retn
```
