# HCEConnectionMgr::SetReceivedApdu(ushort,uchar const *,int,ulong)

- ea: `0x180068afc`
- end: `0x180068d4c`
- name: `?SetReceivedApdu@HCEConnectionMgr@@QEAAJGPEBEHK@Z`
- size: `592`
- prototype: `int(HCEConnectionMgr *__hidden this, unsigned __int16, const unsigned __int8 *, int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006db24`

## callees

- `0x180004ec0`
- `0x180005840`
- `0x180068afc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180068c1f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180068c1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068d15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068d15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180068bd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180068bd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068d2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068d2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068b2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068b2f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180068cff`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180068cff`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180068c8d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180068c8d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180068cbe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180068cbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068cc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068cc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068cf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068cf7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall HCEConnectionMgr::SetReceivedApdu(
        HCEConnectionMgr *this,
        unsigned __int16 a2,
        const unsigned __int8 *a3,
        int a4,
        unsigned int a5)
{
  SIZE_T v7; // rdi
  struct _RTL_CRITICAL_SECTION *v9; // r15
  unsigned int v10; // esi
  __int64 *v11; // rax
  __int64 v12; // r14
  size_t v13; // rbx
  void *v14; // rax
  void *v15; // rdi
  __int64 v16; // r13
  _DWORD *v17; // rcx
  _QWORD *v18; // rax
  __int64 **v19; // rdi
  __int64 *i; // rbx
  void *v21; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  void *v24; // rcx
  struct _RTL_CRITICAL_SECTION *v26; // [rsp+20h] [rbp-68h]
  int v27; // [rsp+90h] [rbp+8h]

  v7 = a2;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  v26 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v10 = 0;
  if ( !a3 )
  {
    v10 = -2147467261;
    goto LABEL_34;
  }
  if ( !*((_BYTE *)this + 128) )
  {
    v10 = -2147019873;
    goto LABEL_34;
  }
  if ( !*((_QWORD *)this + 15)
    || (v11 = (__int64 *)*((_QWORD *)this + 14), v12 = *v11, !*(_BYTE *)(*v11 + 40))
    || *(_QWORD *)(v12 + 232) >= (unsigned __int64)*(unsigned __int16 *)(v12 + 256) )
  {
    v10 = -2134834683;
    goto LABEL_34;
  }
  if ( a4 )
    *(_DWORD *)(v12 + 80) = a5;
  if ( (unsigned int)(*(_DWORD *)(v12 + 16) - 1) <= 1 || *((_BYTE *)this + 24) )
  {
    v27 = *(_DWORD *)(v12 + 80);
    v13 = v7;
    v14 = CoTaskMemAlloc(v7);
    v15 = v14;
    if ( !v14 )
    {
      v10 = -2147024882;
      goto LABEL_34;
    }
    if ( v13 )
      memcpy_0(v14, a3, v13);
    try
    {
      if ( *(_QWORD *)(v12 + 232) == 0x666666666666666LL )
        std::_Xlength_error("list too long");
      v16 = *(_QWORD *)(v12 + 224);
      v17 = operator new(0x28u);
      v17[4] = a4;
      v17[5] = v27;
      *((_WORD *)v17 + 12) = a2;
      *((_QWORD *)v17 + 4) = v15;
      ++*(_QWORD *)(v12 + 232);
      v18 = *(_QWORD **)(v16 + 8);
      *(_QWORD *)v17 = v16;
      *((_QWORD *)v17 + 1) = v18;
      *(_QWORD *)(v16 + 8) = v17;
      *v18 = v17;
      v19 = *(__int64 ***)(v12 + 64);
      for ( i = *v19; i != (__int64 *)v19; i = (__int64 *)*i )
      {
        if ( !*((_DWORD *)i + 5) )
          SetEvent((HANDLE)i[4]);
      }
      if ( *(_QWORD *)(v12 + 232) < (unsigned __int64)*(unsigned __int16 *)(v12 + 256) )
        goto LABEL_34;
      v21 = *(void **)(v12 + 248);
      if ( !v21 )
      {
        EventW = CreateEventW(0, 1, 0, 0);
        if ( EventW )
        {
          v24 = *(void **)(v12 + 248);
          *(_QWORD *)(v12 + 248) = EventW;
          if ( (unsigned __int64)v24 + 1 > 1 )
            CloseHandle(v24);
          goto LABEL_34;
        }
        goto LABEL_27;
      }
      if ( !ResetEvent(v21) )
      {
LABEL_27:
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v10 = LastError;
      }
    }
    catch ( std::bad_alloc )
    {
      v9 = v26;
      v10 = -2147024882;
    }
  }
LABEL_34:
  LeaveCriticalSection(v9);
  return v10;
}

```

## disassembly

```asm
0x180068afc  mov     rax, rsp
0x180068aff  mov     [rax+18h], rbx
0x180068b03  mov     [rax+20h], rsi
0x180068b07  mov     [rax+10h], dx
0x180068b0b  push    rdi
0x180068b0c  push    r12
0x180068b0e  push    r13
0x180068b10  push    r14
0x180068b12  push    r15
0x180068b14  sub     rsp, 60h
0x180068b18  mov     r12d, r9d
0x180068b1b  mov     r13, r8
0x180068b1e  movzx   edi, dx
0x180068b21  mov     rbx, rcx
0x180068b24  lea     r15, [rcx+30h]
0x180068b28  mov     [rax-68h], r15
0x180068b2c  mov     rcx, r15; lpCriticalSection
0x180068b2f  call    cs:__imp_EnterCriticalSection
0x180068b35  mov     [rsp+88h+var_60], 1
0x180068b3a  xor     esi, esi
0x180068b3c  test    r13, r13
0x180068b3f  jnz     short loc_180068B4B
0x180068b41  mov     esi, 80004003h
0x180068b46  jmp     loc_180068D27
0x180068b4b  cmp     [rbx+80h], sil
0x180068b52  jnz     short loc_180068B5E
0x180068b54  mov     esi, 8007139Fh
0x180068b59  jmp     loc_180068D27
0x180068b5e  cmp     [rbx+78h], rsi
0x180068b62  jnz     short loc_180068B6E
0x180068b64  mov     esi, 80C10205h
0x180068b69  jmp     loc_180068D27
0x180068b6e  mov     rax, [rbx+70h]
0x180068b72  mov     r14, [rax]
0x180068b75  cmp     [r14+28h], sil
0x180068b79  jz      short loc_180068B64
0x180068b7b  movzx   eax, word ptr [r14+100h]
0x180068b83  cmp     [r14+0E8h], rax
0x180068b8a  jnb     short loc_180068B64
0x180068b8c  test    r12d, r12d
0x180068b8f  jz      short loc_180068B9C
0x180068b91  mov     eax, [rsp+88h+arg_20]
0x180068b98  mov     [r14+50h], eax
0x180068b9c  mov     eax, [r14+10h]
0x180068ba0  dec     eax
0x180068ba2  cmp     eax, 1
0x180068ba5  jbe     short loc_180068BB1
0x180068ba7  cmp     [rbx+18h], sil
0x180068bab  jz      loc_180068D27
0x180068bb1  mov     [rsp+88h+var_40], di
0x180068bb6  mov     [rsp+88h+var_48], r12d
0x180068bbb  mov     eax, [r14+50h]
0x180068bbf  mov     [rsp+88h+arg_0], eax
0x180068bc6  mov     [rsp+88h+var_44], eax
0x180068bca  mov     rbx, rdi
0x180068bcd  mov     rcx, rdi; cb
0x180068bd0  call    cs:__imp_CoTaskMemAlloc
0x180068bd6  mov     rdi, rax
0x180068bd9  mov     [rsp+88h+pv], rax
0x180068bde  test    rax, rax
0x180068be1  jnz     short loc_180068BED
0x180068be3  mov     esi, 8007000Eh
0x180068be8  jmp     loc_180068D27
0x180068bed  test    rbx, rbx
0x180068bf0  jz      short loc_180068C01
0x180068bf2  mov     r8, rbx; Size
0x180068bf5  mov     rdx, r13; Src
0x180068bf8  mov     rcx, rdi; void *
0x180068bfb  call    memcpy_0
0x180068c00  nop
0x180068c01  lea     rbx, [r14+0E0h]
0x180068c08  mov     rax, 666666666666666h
0x180068c12  cmp     [rbx+8], rax
0x180068c16  jnz     short loc_180068C25
0x180068c18  lea     rcx, aListTooLong; "list too long"
0x180068c1f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180068c25  mov     r13, [rbx]
0x180068c28  mov     [rsp+88h+var_58], rbx
0x180068c2d  mov     [rsp+88h+var_50], rsi
0x180068c32  mov     ecx, 28h ; '('; Size
0x180068c37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180068c3c  mov     rcx, rax
0x180068c3f  mov     [rax+10h], r12d
0x180068c43  mov     eax, [rsp+88h+arg_0]
0x180068c4a  mov     [rcx+14h], eax
0x180068c4d  movzx   eax, [rsp+88h+arg_8]
0x180068c55  mov     [rcx+18h], ax
0x180068c59  mov     [rsp+88h+pv], rsi
0x180068c5e  mov     [rcx+20h], rdi
0x180068c62  inc     qword ptr [rbx+8]
0x180068c66  mov     rax, [r13+8]
0x180068c6a  mov     [rcx], r13
0x180068c6d  mov     [rcx+8], rax
0x180068c71  mov     [r13+8], rcx
0x180068c75  mov     [rax], rcx
0x180068c78  mov     rdi, [r14+40h]
0x180068c7c  mov     rbx, [rdi]
0x180068c7f  cmp     rbx, rdi
0x180068c82  jz      short loc_180068C98
0x180068c84  cmp     [rbx+14h], esi
0x180068c87  jnz     short loc_180068C93
0x180068c89  mov     rcx, [rbx+20h]; hEvent
0x180068c8d  call    cs:__imp_SetEvent
0x180068c93  mov     rbx, [rbx]
0x180068c96  jmp     short loc_180068C7F
0x180068c98  movzx   eax, word ptr [r14+100h]
0x180068ca0  cmp     [r14+0E8h], rax
0x180068ca7  jb      short loc_180068D27
0x180068ca9  mov     rcx, [r14+0F8h]; hEvent
0x180068cb0  test    rcx, rcx
0x180068cb3  jnz     short loc_180068CFF
0x180068cb5  xor     r9d, r9d; lpName
0x180068cb8  xor     r8d, r8d; bInitialState
0x180068cbb  lea     edx, [rcx+1]; bManualReset
0x180068cbe  call    cs:__imp_CreateEventW
0x180068cc4  test    rax, rax
0x180068cc7  jnz     short loc_180068CDF
0x180068cc9  call    cs:__imp_GetLastError
0x180068ccf  test    eax, eax
0x180068cd1  jle     short loc_180068CDB
0x180068cd3  movzx   eax, ax
0x180068cd6  or      eax, 80070000h
0x180068cdb  mov     esi, eax
0x180068cdd  jmp     short loc_180068D27
0x180068cdf  mov     rcx, [r14+0F8h]; hObject
0x180068ce6  mov     [r14+0F8h], rax
0x180068ced  lea     rax, [rcx+1]
0x180068cf1  cmp     rax, 1
0x180068cf5  jbe     short loc_180068D27
0x180068cf7  call    cs:__imp_CloseHandle
0x180068cfd  jmp     short loc_180068D27
0x180068cff  call    cs:__imp_ResetEvent
0x180068d05  test    eax, eax
0x180068d07  jnz     short loc_180068D27
0x180068d09  jmp     short loc_180068CC9
0x180068d0b  mov     rcx, [rsp+88h+pv]; pv
0x180068d10  test    rcx, rcx
0x180068d13  jz      short loc_180068D1B
0x180068d15  call    cs:__imp_CoTaskMemFree
0x180068d1b  mov     r15, [rsp+88h+var_68]
0x180068d20  mov     esi, [rsp+88h+arg_0]
0x180068d27  mov     rcx, r15; lpCriticalSection
0x180068d2a  call    cs:__imp_LeaveCriticalSection
0x180068d30  mov     eax, esi
0x180068d32  lea     r11, [rsp+88h+var_28]
0x180068d37  mov     rbx, [r11+40h]
0x180068d3b  mov     rsi, [r11+48h]
0x180068d3f  mov     rsp, r11
0x180068d42  pop     r15
0x180068d44  pop     r14
0x180068d46  pop     r13
0x180068d48  pop     r12
0x180068d4a  pop     rdi
0x180068d4b  retn
```
