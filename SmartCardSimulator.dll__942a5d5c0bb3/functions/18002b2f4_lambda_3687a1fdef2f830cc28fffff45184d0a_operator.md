# _lambda_3687a1fdef2f830cc28fffff45184d0a_::operator()

- ea: `0x18002b2f4`
- end: `0x18002b42f`
- name: `_lambda_3687a1fdef2f830cc28fffff45184d0a_::operator()`
- size: `315`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18002f068`
- `0x1800303cc`

## callees

- `0x180009878`
- `0x1800099c0`
- `0x180009a5c`
- `0x18002b2f4`
- `0x180039eac`
- `0x18003b1f8`
- `0x1800586c6`
- `0x180058700`

## string_xrefs

- `0x18002b3ea`: `FileSystem::ElementaryFile::DeleteDataObject`

## pseudocode

```c
PVOID __fastcall lambda_3687a1fdef2f830cc28fffff45184d0a_::operator()(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // r8
  __int64 v4; // r9
  PVOID result; // rax
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rsi
  int *v9; // rax
  int v10; // r14d
  int v11; // r15d
  int v12; // r12d
  char v13; // al
  _QWORD v14[2]; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v15[64]; // [rsp+70h] [rbp-88h] BYREF
  __int64 v16; // [rsp+B0h] [rbp-48h] BYREF

  memset_0(v15, 0, sizeof(v15));
  if ( **(_BYTE **)a1 )
    v2 = ReportIndentTracker::Enter();
  else
    v2 = ReportIndentTracker::Exit();
  v14[0] = v15;
  v14[1] = &v16;
  LOBYTE(v4) = **(_BYTE **)a1 != 0 ? 62 : 60;
  ReportIndentTracker::Format(v14, v2, v3, v4);
  result = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    try
    {
      v6 = *(_QWORD *)(a1 + 32);
      v7 = *(_QWORD *)(v6 + 32);
      v8 = *(_QWORD *)(v6 + 16);
      v9 = *(int **)(a1 + 24);
      v10 = v9[2];
      v11 = v9[1];
      v12 = *v9;
      v13 = Asn1Tag::make(*(const struct Asn1Tag::type **)(a1 + 16));
      result = (PVOID)WPP_SF_ssDDLLLss(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        (__int64)"FileSystem::ElementaryFile::DeleteDataObject",
                        *(_WORD *)(*(_QWORD *)(a1 + 8) + 36LL),
                        v13,
                        v12,
                        v11,
                        v10,
                        v8,
                        v7);
    }
    catch ( std::bad_alloc )
    {
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002b2f4  push    rbx
0x18002b2f6  push    rsi
0x18002b2f7  push    rdi
0x18002b2f8  push    r12
0x18002b2fa  push    r14
0x18002b2fc  push    r15
0x18002b2fe  sub     rsp, 0C8h
0x18002b305  mov     rax, cs:__security_cookie
0x18002b30c  xor     rax, rsp
0x18002b30f  mov     [rsp+0F8h+var_48], rax
0x18002b317  mov     rbx, rcx
0x18002b31a  xor     edx, edx; Val
0x18002b31c  lea     r8d, [rdx+40h]; Size
0x18002b320  lea     rcx, [rsp+0F8h+var_88]; void *
0x18002b325  call    memset_0
0x18002b32a  mov     rax, [rbx]
0x18002b32d  cmp     byte ptr [rax], 0
0x18002b330  jz      short loc_18002B339
0x18002b332  call    ?Enter@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Enter(void)
0x18002b337  jmp     short loc_18002B33E
0x18002b339  call    ?Exit@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Exit(void)
0x18002b33e  mov     edx, eax
0x18002b340  lea     rax, [rsp+0F8h+var_88]
0x18002b345  mov     [rsp+0F8h+var_98], rax
0x18002b34a  lea     rax, [rsp+0F8h+var_48]
0x18002b352  mov     [rsp+0F8h+var_90], rax
0x18002b357  mov     rax, [rbx]
0x18002b35a  mov     cl, [rax]
0x18002b35c  neg     cl
0x18002b35e  sbb     r9b, r9b
0x18002b361  and     r9b, 2
0x18002b365  add     r9b, 3Ch ; '<'
0x18002b369  lea     rcx, [rsp+0F8h+var_98]
0x18002b36e  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x18002b373  lea     rcx, WPP_GLOBAL_Control
0x18002b37a  mov     rax, cs:WPP_GLOBAL_Control
0x18002b381  cmp     rax, rcx
0x18002b384  jz      loc_18002B40C
0x18002b38a  test    byte ptr [rax+1Ch], 2
0x18002b38e  jz      short loc_18002B40C
0x18002b390  cmp     byte ptr [rax+19h], 5
0x18002b394  jb      short loc_18002B40C
0x18002b396  mov     rax, [rbx+20h]
0x18002b39a  mov     rdi, [rax+20h]
0x18002b39e  mov     rsi, [rax+10h]
0x18002b3a2  mov     rax, [rbx+18h]
0x18002b3a6  mov     r14d, [rax+8]
0x18002b3aa  mov     r15d, [rax+4]
0x18002b3ae  mov     r12d, [rax]
0x18002b3b1  mov     rcx, [rbx+10h]; struct Asn1Tag::type *
0x18002b3b5  call    ?make@Asn1Tag@@SAKAEBUtype@1@@Z; Asn1Tag::make(Asn1Tag::type const &)
0x18002b3ba  mov     rcx, [rbx+8]
0x18002b3be  movzx   r8d, word ptr [rcx+24h]
0x18002b3c3  mov     edx, 37h ; '7'
0x18002b3c8  mov     [rsp+0F8h+var_A0], rdi; __int64
0x18002b3cd  mov     [rsp+0F8h+var_A8], rsi; __int64
0x18002b3d2  mov     dword ptr [rsp+0F8h+var_B0], r14d; char
0x18002b3d7  mov     dword ptr [rsp+0F8h+var_B8], r15d; char
0x18002b3dc  mov     dword ptr [rsp+0F8h+var_C0], r12d; char
0x18002b3e1  mov     dword ptr [rsp+0F8h+var_C8], eax; char
0x18002b3e5  mov     dword ptr [rsp+0F8h+var_D0], r8d; char
0x18002b3ea  lea     rax, aFilesystemElem_16; "FileSystem::ElementaryFile::DeleteDataO"...
0x18002b3f1  mov     [rsp+0F8h+var_D8], rax; __int64
0x18002b3f6  lea     r9, [rsp+0F8h+var_88]
0x18002b3fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b402  mov     rcx, [rcx+10h]; LoggerHandle
0x18002b406  call    WPP_SF_ssDDLLLss
0x18002b40b  nop
0x18002b40c  jmp     short $+2
0x18002b40e  mov     rcx, [rsp+0F8h+var_48]
0x18002b416  xor     rcx, rsp; StackCookie
0x18002b419  call    __security_check_cookie
0x18002b41e  add     rsp, 0C8h
0x18002b425  pop     r15
0x18002b427  pop     r14
0x18002b429  pop     r12
0x18002b42b  pop     rdi
0x18002b42c  pop     rsi
0x18002b42d  pop     rbx
0x18002b42e  retn
```
