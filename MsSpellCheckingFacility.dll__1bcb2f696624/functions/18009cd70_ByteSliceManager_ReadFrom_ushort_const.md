# ByteSliceManager::ReadFrom(ushort const *)

- ea: `0x18009cd70`
- end: `0x18009ce28`
- name: `?ReadFrom@ByteSliceManager@@UEAAXPEBG@Z`
- size: `184`
- prototype: `void(ByteSliceManager *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18005a400`
- `0x180061320`
- `0x18009cd70`
- `0x18009cf18`
- `0x18009d8a4`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18009cdc2`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18009cdc2`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18009cdfb`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18009cdfb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ByteSliceManager::ReadFrom(ByteSliceManager *this, const unsigned __int16 *a2, int *a3)
{
  const wchar_t *v4; // r9
  int v5; // ecx
  int v6; // [rsp+20h] [rbp-E8h] BYREF
  FILE *Stream; // [rsp+28h] [rbp-E0h] BYREF
  GUID v8; // [rsp+30h] [rbp-D8h] BYREF
  _BYTE v9[80]; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v10[96]; // [rsp+90h] [rbp-78h] BYREF

  v6 = 0;
  CExceptionSetup::CExceptionSetup((CExceptionSetup *)v10, &v6, a3, (bool)a2);
  Stream = 0;
  if ( _wfopen_s(&Stream, v4, L"rb") )
  {
    v5 = -2147467259;
    v6 = -2147467259;
  }
  else
  {
    v5 = v6;
  }
  ThrowIfFailed(v5);
  try
  {
    (*(void (**)(void))(*(_QWORD *)this + 32LL))();
    fclose(Stream);
    CExceptionSetup::~CExceptionSetup((CExceptionSetup *)v10);
  }
  catch ( CNLException v9 )
  {
    fclose(Stream);
    v8 = GUID_NULL;
    CNLException::HandleIt((CNLException *)v9, (struct CExceptionSetup *)v10, &v8);
    CNLException::Throw((CNLException *)v9);
  }
}

```

## disassembly

```asm
0x18009cd70  mov     r11, rsp
0x18009cd73  push    rbx
0x18009cd74  sub     rsp, 100h
0x18009cd7b  mov     rax, cs:__security_cookie
0x18009cd82  xor     rax, rsp
0x18009cd85  mov     [rsp+108h+var_18], rax
0x18009cd8d  mov     r9, rdx; bool
0x18009cd90  mov     rbx, rcx
0x18009cd93  mov     [rsp+108h+var_E8], 0
0x18009cd9b  lea     rdx, [rsp+108h+var_E8]; int *
0x18009cda0  lea     rcx, [r11-78h]; this
0x18009cda4  call    ??0CExceptionSetup@@QEAA@PEAJPEAH_N@Z; CExceptionSetup::CExceptionSetup(long *,int *,bool)
0x18009cda9  nop
0x18009cdaa  mov     [rsp+108h+Stream], 0
0x18009cdb3  lea     r8, aRb; "rb"
0x18009cdba  mov     rdx, r9; FileName
0x18009cdbd  lea     rcx, [rsp+108h+Stream]; Stream
0x18009cdc2  call    cs:__imp__wfopen_s
0x18009cdc8  test    eax, eax
0x18009cdca  jz      short loc_18009CDD7
0x18009cdcc  mov     ecx, 80004005h
0x18009cdd1  mov     [rsp+108h+var_E8], ecx
0x18009cdd5  jmp     short loc_18009CDDB
0x18009cdd7  mov     ecx, [rsp+108h+var_E8]; int
0x18009cddb  call    ?ThrowIfFailed@@YAXJ@Z; ThrowIfFailed(long)
0x18009cde0  nop
0x18009cde1  mov     rax, [rbx]
0x18009cde4  mov     rdx, [rsp+108h+Stream]
0x18009cde9  mov     rcx, rbx
0x18009cdec  mov     rax, [rax+20h]
0x18009cdf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cdf5  nop
0x18009cdf6  mov     rcx, [rsp+108h+Stream]; Stream
0x18009cdfb  call    cs:__imp_fclose
0x18009ce01  nop
0x18009ce02  lea     rcx, [rsp+108h+var_78]; this
0x18009ce0a  call    ??1CExceptionSetup@@QEAA@XZ; CExceptionSetup::~CExceptionSetup(void)
0x18009ce0f  mov     rcx, [rsp+108h+var_18]
0x18009ce17  xor     rcx, rsp; StackCookie
0x18009ce1a  call    __security_check_cookie
0x18009ce1f  add     rsp, 100h
0x18009ce26  pop     rbx
0x18009ce27  retn
```
