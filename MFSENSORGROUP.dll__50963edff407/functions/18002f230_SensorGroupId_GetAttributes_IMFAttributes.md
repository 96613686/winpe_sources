# SensorGroupId::GetAttributes(IMFAttributes * *)

- ea: `0x18002f230`
- end: `0x18002f312`
- name: `?GetAttributes@SensorGroupId@@UEAAJPEAPEAUIMFAttributes@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(SensorGroupId *__hidden this, struct IMFAttributes **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005fa0`
- `0x18002f230`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f2a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f2a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f248`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f248`
- `MFPlat!MFCreateAttributes` at `0x18002f277`
- `MFPlat!MFCreateAttributes` at `0x18002f277`

## pseudocode

```c
__int64 __fastcall SensorGroupId::GetAttributes(SensorGroupId *this, struct IMFAttributes **a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  char *v5; // rsi
  IMFAttributes **v6; // rdi
  HRESULT v7; // eax
  unsigned int v8; // ebx
  __int64 v10; // rdx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a2 )
  {
    v5 = (char *)this - 8;
    *a2 = 0;
    v6 = (IMFAttributes **)((char *)this + 168);
    if ( *((_QWORD *)v5 + 22) || (v7 = MFCreateAttributes(v6, 1u), v8 = v7, v7 >= 0) )
    {
      v7 = ((__int64 (__fastcall *)(IMFAttributes *, GUID *, struct IMFAttributes **))(*v6)->lpVtbl->QueryInterface)(
             *v6,
             &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3,
             a2);
      v8 = v7;
      if ( v7 < 0 && g_wppLevels )
      {
        v10 = 128;
        goto LABEL_12;
      }
    }
    else if ( g_wppLevels )
    {
      v10 = 127;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, v5, v7);
    }
  }
  else
  {
    v8 = -2147467261;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        126,
        &WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
        (char *)this - 8,
        -2147467261);
  }
  LeaveCriticalSection(v2);
  return v8;
}

```

## disassembly

```asm
0x18002f230  push    rbx
0x18002f232  push    rbp
0x18002f233  push    rsi
0x18002f234  push    rdi
0x18002f235  push    r14
0x18002f237  sub     rsp, 30h
0x18002f23b  lea     rbp, [rcx+10h]
0x18002f23f  mov     rdi, rcx
0x18002f242  mov     rcx, rbp; lpCriticalSection
0x18002f245  mov     r14, rdx
0x18002f248  call    cs:__imp_EnterCriticalSection
0x18002f24e  test    r14, r14
0x18002f251  jz      short loc_18002F2B7
0x18002f253  lea     rsi, [rdi-8]
0x18002f257  mov     qword ptr [r14], 0
0x18002f25e  add     rdi, 0A8h
0x18002f265  cmp     qword ptr [rsi+0B0h], 0
0x18002f26d  jnz     short loc_18002F283
0x18002f26f  mov     edx, 1; cInitialSize
0x18002f274  mov     rcx, rdi; ppMFAttributes
0x18002f277  call    cs:__imp_MFCreateAttributes
0x18002f27d  mov     ebx, eax
0x18002f27f  test    eax, eax
0x18002f281  js      short loc_18002F2D4
0x18002f283  mov     rcx, [rdi]
0x18002f286  lea     rdx, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x18002f28d  mov     r8, r14
0x18002f290  mov     rax, [rcx]
0x18002f293  mov     rax, [rax]
0x18002f296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f29b  mov     ebx, eax
0x18002f29d  test    eax, eax
0x18002f29f  js      short loc_18002F2E4
0x18002f2a1  mov     rcx, rbp; lpCriticalSection
0x18002f2a4  call    cs:__imp_LeaveCriticalSection
0x18002f2aa  mov     eax, ebx
0x18002f2ac  add     rsp, 30h
0x18002f2b0  pop     r14
0x18002f2b2  pop     rdi
0x18002f2b3  pop     rsi
0x18002f2b4  pop     rbp
0x18002f2b5  pop     rbx
0x18002f2b6  retn
0x18002f2b7  mov     ebx, 80004003h
0x18002f2bc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002f2c3  jb      short loc_18002F2A1
0x18002f2c5  lea     r9, [rdi-8]
0x18002f2c9  mov     [rsp+58h+var_38], ebx
0x18002f2cd  mov     edx, 7Eh ; '~'
0x18002f2d2  jmp     short loc_18002F2F9
0x18002f2d4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002f2db  jb      short loc_18002F2A1
0x18002f2dd  mov     edx, 7Fh
0x18002f2e2  jmp     short loc_18002F2F2
0x18002f2e4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002f2eb  jb      short loc_18002F2A1
0x18002f2ed  mov     edx, 80h
0x18002f2f2  mov     r9, rsi
0x18002f2f5  mov     [rsp+58h+var_38], eax
0x18002f2f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f300  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18002f307  mov     rcx, [rcx+10h]
0x18002f30b  call    WPP_SF_qD
0x18002f310  jmp     short loc_18002F2A1
```
