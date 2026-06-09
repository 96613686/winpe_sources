# EsdSipIsFileSupportedName(ushort *,_GUID *)

- ea: `0x180002150`
- end: `0x180002205`
- name: `?EsdSipIsFileSupportedName@@YAHPEAGPEAU_GUID@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _GUID *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180002150`
- `0x180002568`
- `0x180002a4c`
- `0x180002c08`
- `0x180002d40`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800021e3`
- `KERNEL32!SetLastError` at `0x1800021e3`
- `KERNEL32!GetLastError` at `0x1800021a3`
- `KERNEL32!GetLastError` at `0x1800021a3`

## pseudocode

```c
__int64 __fastcall EsdSipIsFileSupportedName(unsigned __int16 *a1, struct _GUID *a2)
{
  unsigned int v2; // esi
  DWORD LastError; // eax
  GUID *v6; // rcx
  __m128i si128; // [rsp+20h] [rbp-18h] BYREF

  v2 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  if ( a1 && a2 )
  {
    if ( IsSupportedFileType(a1) )
    {
      if ( CFile::Open((CFile *)&si128, a1, 0) && (unsigned int)IsFileObjectSupported((const struct CFile *)&si128) )
      {
        v6 = &GUID_ESDSIP;
        if ( *(_QWORD *)&g_pgSubject.Data1 )
          v6 = *(GUID **)&g_pgSubject.Data1;
        LastError = 0;
        v2 = 1;
        *a2 = *v6;
      }
      else
      {
        LastError = GetLastError();
      }
    }
    else
    {
      LastError = 1630;
    }
  }
  else
  {
    LastError = 87;
  }
  SetLastError(LastError);
  CFile::~CFile((CFile *)&si128);
  return v2;
}

```

## disassembly

```asm
0x180002150  mov     [rsp+arg_0], rbx; EsdSipIsFileSupportedName
0x180002155  mov     [rsp+arg_8], rsi
0x18000215a  push    rdi
0x18000215b  sub     rsp, 30h
0x18000215f  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180002167  xor     esi, esi
0x180002169  mov     rdi, rdx
0x18000216c  mov     rbx, rcx
0x18000216f  movdqu  [rsp+38h+var_18], xmm0
0x180002175  test    rcx, rcx
0x180002178  jz      short loc_1800021DC
0x18000217a  test    rdx, rdx
0x18000217d  jz      short loc_1800021DC
0x18000217f  call    ?IsSupportedFileType@@YA_NPEBG@Z; IsSupportedFileType(ushort const *)
0x180002184  test    al, al
0x180002186  jnz     short loc_18000218F
0x180002188  mov     eax, 65Eh
0x18000218d  jmp     short loc_1800021E1
0x18000218f  xor     r8d, r8d; bool
0x180002192  lea     rcx, [rsp+38h+var_18]; this
0x180002197  mov     rdx, rbx; unsigned __int16 *
0x18000219a  call    ?Open@CFile@@QEAA_NPEBG_N@Z; CFile::Open(ushort const *,bool)
0x18000219f  test    al, al
0x1800021a1  jnz     short loc_1800021AB
0x1800021a3  call    cs:__imp_GetLastError
0x1800021a9  jmp     short loc_1800021E1
0x1800021ab  lea     rcx, [rsp+38h+var_18]; this
0x1800021b0  call    ?IsFileObjectSupported@@YAHAEBVCFile@@@Z; IsFileObjectSupported(CFile const &)
0x1800021b5  test    eax, eax
0x1800021b7  jz      short loc_1800021A3
0x1800021b9  mov     rax, qword ptr cs:?g_pgSubject@@3PEAU_GUID@@EA.Data1; _GUID * g_pgSubject ...
0x1800021c0  lea     rcx, GUID_ESDSIP
0x1800021c7  test    rax, rax
0x1800021ca  cmovnz  rcx, rax
0x1800021ce  xor     eax, eax
0x1800021d0  movups  xmm0, xmmword ptr [rcx]
0x1800021d3  lea     esi, [rax+1]
0x1800021d6  movdqu  xmmword ptr [rdi], xmm0
0x1800021da  jmp     short loc_1800021E1
0x1800021dc  mov     eax, 57h ; 'W'
0x1800021e1  mov     ecx, eax; dwErrCode
0x1800021e3  call    cs:__imp_SetLastError
0x1800021e9  lea     rcx, [rsp+38h+var_18]; this
0x1800021ee  call    ??1CFile@@QEAA@XZ; CFile::~CFile(void)
0x1800021f3  mov     rbx, [rsp+38h+arg_0]
0x1800021f8  mov     eax, esi
0x1800021fa  mov     rsi, [rsp+38h+arg_8]
0x1800021ff  add     rsp, 30h
0x180002203  pop     rdi
0x180002204  retn
```
