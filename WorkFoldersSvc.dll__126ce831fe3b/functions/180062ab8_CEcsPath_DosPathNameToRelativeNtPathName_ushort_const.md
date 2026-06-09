# CEcsPath::DosPathNameToRelativeNtPathName(ushort const *)

- ea: `0x180062ab8`
- end: `0x180062c71`
- name: `?DosPathNameToRelativeNtPathName@CEcsPath@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800d1cc4`

## callees

- `0x180003604`
- `0x180007e10`
- `0x180011314`
- `0x18001137c`
- `0x180015150`
- `0x18001db74`
- `0x180062ab8`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180062b6b`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180062b6b`
- `ntdll!RtlFreeHeap` at `0x180062c13`
- `ntdll!RtlFreeHeap` at `0x180062c13`

## string_xrefs

- `0x180062b32`: `CEcsPath::DosPathNameToRelativeNtPathName`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CEcsPath::DosPathNameToRelativeNtPathName(__int64 a1, const WCHAR *a2)
{
  _BYTE *v3; // rax
  char v4; // al
  int pExceptionObject; // [rsp+24h] [rbp-74h] BYREF
  int v7; // [rsp+28h] [rbp-70h] BYREF
  int v8; // [rsp+2Ch] [rbp-6Ch] BYREF
  const ATL::CAtlException *v9; // [rsp+30h] [rbp-68h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+38h] [rbp-60h] BYREF
  int v11; // [rsp+48h] [rbp-50h] BYREF
  int v12; // [rsp+4Ch] [rbp-4Ch]
  char v13; // [rsp+50h] [rbp-48h]
  const char *v14; // [rsp+58h] [rbp-40h]
  __int64 v15; // [rsp+60h] [rbp-38h]

  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, WPP_5d95a7213829360425c4708bf03e9463_Traceguids);
      v3 = WPP_GLOBAL_Control;
    }
  }
  if ( (v3[68] & 2) != 0 && v3[65] >= 6u )
  {
    v4 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v4 = 0;
LABEL_9:
  v11 = 0;
  v12 = 609;
  v13 = v4;
  v14 = "CEcsPath::DosPathNameToRelativeNtPathName";
  v15 = 0;
  std::wstring::wstring(a1);
  NtName = 0;
  if ( !RtlDosPathNameToRelativeNtPathName_U(a2, &NtName, 0, 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, WPP_5d95a7213829360425c4708bf03e9463_Traceguids, a2);
    }
    v11 = -2134376423;
    HIWORD(v12) = 618;
    pExceptionObject = -2134376423;
    throw (long *)&pExceptionObject;
  }
  try
  {
    std::wstring::assign(a1, NtName.Buffer, (unsigned __int64)NtName.Length >> 1);
  }
  catch ( long v8 )
  {
    v11 = v8;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v12) = 627;
    v11 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v12) = 627;
    v11 = -2147418113;
  }
  catch ( const ATL::CAtlException *v9 )
  {
    HIWORD(v12) = 627;
    v11 = *(_DWORD *)v9;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtName.Buffer);
  if ( v11 < 0 )
  {
    HIWORD(v12) = 631;
    v7 = v11;
    throw (long *)&v7;
  }
  LOWORD(v12) = 631;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v11);
  return a1;
}

```

## disassembly

```asm
0x180062ab8  mov     [rsp+arg_0], rcx
0x180062abd  push    rbx
0x180062abe  push    rsi
0x180062abf  push    rdi
0x180062ac0  push    r14
0x180062ac2  sub     rsp, 78h
0x180062ac6  mov     rsi, rdx
0x180062ac9  mov     ebx, 1
0x180062ace  mov     [rsp+98h+var_78], ebx
0x180062ad2  lea     r14, WPP_GLOBAL_Control
0x180062ad9  mov     rax, cs:WPP_GLOBAL_Control
0x180062ae0  cmp     rax, r14
0x180062ae3  jz      short loc_180062B0B
0x180062ae5  test    byte ptr [rax+44h], 2
0x180062ae9  jz      short loc_180062B1D
0x180062aeb  cmp     byte ptr [rax+41h], 6
0x180062aef  jb      short loc_180062B0B
0x180062af1  lea     edx, [rbx+15h]
0x180062af4  lea     r8, WPP_5d95a7213829360425c4708bf03e9463_Traceguids
0x180062afb  mov     rcx, [rax+38h]
0x180062aff  call    WPP_SF_
0x180062b04  mov     rax, cs:WPP_GLOBAL_Control
0x180062b0b  test    byte ptr [rax+44h], 2
0x180062b0f  jz      short loc_180062B1D
0x180062b11  cmp     byte ptr [rax+41h], 6
0x180062b15  jb      short loc_180062B1D
0x180062b17  mov     al, bl
0x180062b19  xor     edi, edi
0x180062b1b  jmp     short loc_180062B22
0x180062b1d  xor     edi, edi
0x180062b1f  mov     al, dil
0x180062b22  mov     [rsp+98h+var_50], edi
0x180062b26  mov     [rsp+98h+var_4C], 261h
0x180062b2e  mov     [rsp+98h+var_48], al
0x180062b32  lea     rax, aCecspathDospat; "CEcsPath::DosPathNameToRelativeNtPathNa"...
0x180062b39  mov     [rsp+98h+var_40], rax
0x180062b3e  mov     [rsp+98h+var_38], rdi
0x180062b43  mov     rcx, [rsp+98h+arg_0]
0x180062b4b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180062b50  nop
0x180062b51  mov     [rsp+98h+var_78], ebx
0x180062b55  xorps   xmm0, xmm0
0x180062b58  movups  xmmword ptr [rsp+98h+NtName.Length], xmm0
0x180062b5d  xor     r9d, r9d; RelativeName
0x180062b60  xor     r8d, r8d; PartName
0x180062b63  lea     rdx, [rsp+98h+NtName]; NtName
0x180062b68  mov     rcx, rsi; DosName
0x180062b6b  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x180062b71  test    al, al
0x180062b73  jnz     short loc_180062BD6
0x180062b75  mov     rcx, cs:WPP_GLOBAL_Control
0x180062b7c  cmp     rcx, r14
0x180062b7f  jz      short loc_180062BA5
0x180062b81  test    byte ptr [rcx+44h], 2
0x180062b85  jz      short loc_180062BA5
0x180062b87  cmp     byte ptr [rcx+41h], 2
0x180062b8b  jb      short loc_180062BA5
0x180062b8d  mov     edx, 17h
0x180062b92  mov     r9, rsi
0x180062b95  lea     r8, WPP_5d95a7213829360425c4708bf03e9463_Traceguids
0x180062b9c  mov     rcx, [rcx+38h]
0x180062ba0  call    WPP_SF_S
0x180062ba5  mov     eax, [rsp+98h+var_50]
0x180062ba9  mov     [rsp+98h+var_50], eax
0x180062bad  mov     ecx, 80C80019h
0x180062bb2  mov     [rsp+98h+var_50], ecx
0x180062bb6  mov     eax, 26Ah
0x180062bbb  mov     word ptr [rsp+98h+var_4C+2], ax
0x180062bc0  mov     [rsp+98h+pExceptionObject], ecx
0x180062bc4  lea     rdx, _TI1J; pThrowInfo
0x180062bcb  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180062bd0  call    _CxxThrowException_0
0x180062bd6  movzx   r8d, [rsp+98h+NtName.Length]
0x180062bdc  shr     r8, 1
0x180062bdf  mov     rdx, [rsp+98h+NtName.Buffer]
0x180062be4  mov     rcx, [rsp+98h+arg_0]
0x180062bec  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x180062bf1  nop
0x180062bf2  jmp     short loc_180062BFF
0x180062bf4  jmp     short loc_180062BFA
0x180062bf6  jmp     short loc_180062BFA
0x180062bf8  jmp     short $+2
0x180062bfa  mov     ebx, 1
0x180062bff  mov     rcx, gs:60h
0x180062c08  mov     r8, [rsp+98h+NtName.Buffer]; P
0x180062c0d  xor     edx, edx; Flags
0x180062c0f  mov     rcx, [rcx+30h]; HeapHandle
0x180062c13  call    cs:__imp_RtlFreeHeap
0x180062c19  mov     eax, [rsp+98h+var_50]
0x180062c1d  mov     [rsp+98h+var_50], eax
0x180062c21  mov     [rsp+98h+var_50], eax
0x180062c25  mov     ecx, 277h
0x180062c2a  test    eax, eax
0x180062c2c  jns     short loc_180062C49
0x180062c2e  mov     word ptr [rsp+98h+var_4C+2], cx
0x180062c33  mov     [rsp+98h+var_70], eax
0x180062c37  lea     rdx, _TI1J; pThrowInfo
0x180062c3e  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x180062c43  call    _CxxThrowException_0
0x180062c49  mov     word ptr [rsp+98h+var_4C], cx
0x180062c4e  and     ebx, 0FFFFFFFEh
0x180062c51  mov     [rsp+98h+var_78], ebx
0x180062c55  lea     rcx, [rsp+98h+var_50]; this
0x180062c5a  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180062c5f  mov     rax, [rsp+98h+arg_0]
0x180062c67  add     rsp, 78h
0x180062c6b  pop     r14
0x180062c6d  pop     rdi
0x180062c6e  pop     rsi
0x180062c6f  pop     rbx
0x180062c70  retn
```
