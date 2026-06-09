# CMFTSimpleBase::GetInputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x180057740`
- end: `0x180057834`
- name: `?GetInputAvailableType@CMFTSimpleBase@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `244`
- prototype: `__int64 __fastcall(CMFTSimpleBase *__hidden this, unsigned int, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002f9e8`
- `0x180036d70`
- `0x180057740`
- `0x1800960c0`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800577c3`
- `MFPlat!MFCreateMediaType` at `0x1800577c3`

## pseudocode

```c
__int64 __fastcall CMFTSimpleBase::GetInputAvailableType(
        CMFTSimpleBase *this,
        int a2,
        int a3,
        struct IMFMediaType **a4)
{
  HRESULT v8; // ebx
  int v9; // edx
  unsigned int i; // ecx
  __int64 v11; // r14
  __int64 v12; // rcx
  _BYTE v14[56]; // [rsp+20h] [rbp-38h] BYREF

  CMFTSimpleBase::LockIt::LockIt((CMFTSimpleBase::LockIt *)v14, this);
  if ( a2 )
  {
    v8 = -1072875853;
    goto LABEL_19;
  }
  if ( *((_DWORD *)this + 36) == 1 && !*((_QWORD *)this + 10) )
  {
    v8 = -1072861856;
    goto LABEL_19;
  }
  if ( !*((_DWORD *)this + 2) )
  {
    v8 = -2147467263;
    goto LABEL_19;
  }
  v9 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)this + 2) )
    {
      v8 = -1072875847;
      goto LABEL_19;
    }
    v11 = 2LL * i;
    if ( *(_DWORD *)(*((_QWORD *)this + 2) + 16LL * i + 8) )
      break;
LABEL_13:
    ;
  }
  if ( v9 != a3 )
  {
    ++v9;
    goto LABEL_13;
  }
  v8 = MFCreateMediaType(a4);
  if ( v8 >= 0 )
  {
    _mm_lfence();
    v12 = *(_QWORD *)(*((_QWORD *)this + 2) + 8 * v11);
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 256LL))(v12, *a4);
    if ( v8 < 0 )
    {
      if ( *a4 )
      {
        ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
        *a4 = 0;
      }
    }
  }
LABEL_19:
  CMFTSimpleBase::LockIt::~LockIt((CMFTSimpleBase::LockIt *)v14);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180057740  push    rbx
0x180057742  push    rbp
0x180057743  push    rsi
0x180057744  push    rdi
0x180057745  push    r14
0x180057747  sub     rsp, 30h
0x18005774b  mov     ebx, edx
0x18005774d  mov     rdi, rcx
0x180057750  mov     rdx, rcx; struct CMFTSimpleBase *
0x180057753  mov     rsi, r9
0x180057756  lea     rcx, [rsp+58h+var_38]; this
0x18005775b  mov     ebp, r8d
0x18005775e  call    ??0LockIt@CMFTSimpleBase@@QEAA@PEAV1@@Z; CMFTSimpleBase::LockIt::LockIt(CMFTSimpleBase *)
0x180057763  test    ebx, ebx
0x180057765  jz      short loc_180057771
0x180057767  mov     ebx, 0C00D36B3h
0x18005776c  jmp     loc_18005781C
0x180057771  cmp     dword ptr [rdi+90h], 1
0x180057778  jnz     short loc_18005778B
0x18005777a  cmp     qword ptr [rdi+50h], 0
0x18005777f  jnz     short loc_18005778B
0x180057781  mov     ebx, 0C00D6D60h
0x180057786  jmp     loc_18005781C
0x18005778b  cmp     dword ptr [rdi+8], 0
0x18005778f  jnz     short loc_18005779B
0x180057791  mov     ebx, 80004001h
0x180057796  jmp     loc_18005781C
0x18005779b  xor     edx, edx
0x18005779d  xor     ecx, ecx
0x18005779f  cmp     ecx, [rdi+8]
0x1800577a2  jnb     short loc_180057817
0x1800577a4  mov     rax, [rdi+10h]
0x1800577a8  mov     r14d, ecx
0x1800577ab  add     r14, r14
0x1800577ae  cmp     dword ptr [rax+r14*8+8], 0
0x1800577b4  jz      short loc_1800577BC
0x1800577b6  cmp     edx, ebp
0x1800577b8  jz      short loc_1800577C0
0x1800577ba  inc     edx
0x1800577bc  inc     ecx
0x1800577be  jmp     short loc_18005779F
0x1800577c0  mov     rcx, rsi; ppMFType
0x1800577c3  call    cs:__imp_MFCreateMediaType
0x1800577ca  nop     dword ptr [rax+rax+00h]
0x1800577cf  mov     ebx, eax
0x1800577d1  test    eax, eax
0x1800577d3  js      short loc_18005781C
0x1800577d5  lfence
0x1800577d8  mov     rax, [rdi+10h]
0x1800577dc  mov     rdx, [rsi]
0x1800577df  mov     rcx, [rax+r14*8]
0x1800577e3  mov     rax, [rcx]
0x1800577e6  mov     rax, [rax+100h]
0x1800577ed  call    cs:__guard_dispatch_icall_fptr
0x1800577f3  mov     ebx, eax
0x1800577f5  test    eax, eax
0x1800577f7  jns     short loc_18005781C
0x1800577f9  mov     rcx, [rsi]
0x1800577fc  test    rcx, rcx
0x1800577ff  jz      short loc_18005781C
0x180057801  mov     rax, [rcx]
0x180057804  mov     rax, [rax+10h]
0x180057808  call    cs:__guard_dispatch_icall_fptr
0x18005780e  mov     qword ptr [rsi], 0
0x180057815  jmp     short loc_18005781C
0x180057817  mov     ebx, 0C00D36B9h
0x18005781c  lea     rcx, [rsp+58h+var_38]; this
0x180057821  call    ??1LockIt@CMFTSimpleBase@@QEAA@XZ; CMFTSimpleBase::LockIt::~LockIt(void)
0x180057826  mov     eax, ebx
0x180057828  add     rsp, 30h
0x18005782c  pop     r14
0x18005782e  pop     rdi
0x18005782f  pop     rsi
0x180057830  pop     rbp
0x180057831  pop     rbx
0x180057832  retn
```
