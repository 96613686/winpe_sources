# CMetadataRDFReaderWriter::GetClassID(_GUID *)

- ea: `0x180023610`
- end: `0x18002367a`
- name: `?GetClassID@CMetadataRDFReaderWriter@@UEAAJPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x1800058c0`
- `0x18000f1d0`
- `0x1800171c4`
- `0x180023610`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::GetClassID(CMetadataRDFReaderWriter *this, struct _GUID *a2)
{
  unsigned int v4; // ebx
  char *v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = (char *)this + 32;
  CMTALock::Enter((CMetadataRDFReaderWriter *)((char *)this + 32));
  if ( a2 )
  {
    v4 = 0;
    *a2 = *(struct _GUID *)*((_QWORD *)this + 19);
  }
  else
  {
    v4 = -2147024809;
    if ( g_doStackCaptures )
      DoStackCapture(-2147024809);
  }
  CGuard<CMTALock>::~CGuard<CMTALock>(&v6);
  return v4;
}

```

## disassembly

```asm
0x180023610  mov     [rsp+arg_8], rbx
0x180023615  mov     [rsp+arg_10], rsi
0x18002361a  push    rdi
0x18002361b  sub     rsp, 20h
0x18002361f  mov     rsi, rcx
0x180023622  mov     rdi, rdx
0x180023625  add     rcx, 20h ; ' '; this
0x180023629  mov     [rsp+28h+arg_0], rcx
0x18002362e  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180023633  test    rdi, rdi
0x180023636  jnz     short loc_18002364E
0x180023638  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18002363e  mov     ebx, 80070057h
0x180023643  jz      short loc_18002365E
0x180023645  mov     ecx, ebx; int
0x180023647  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002364c  jmp     short loc_18002365E
0x18002364e  mov     rcx, [rsi+98h]
0x180023655  xor     ebx, ebx
0x180023657  movups  xmm0, xmmword ptr [rcx]
0x18002365a  movdqu  xmmword ptr [rdi], xmm0
0x18002365e  lea     rcx, [rsp+28h+arg_0]
0x180023663  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x180023668  mov     rsi, [rsp+28h+arg_10]
0x18002366d  mov     eax, ebx
0x18002366f  mov     rbx, [rsp+28h+arg_8]
0x180023674  add     rsp, 20h
0x180023678  pop     rdi
0x180023679  retn
```
