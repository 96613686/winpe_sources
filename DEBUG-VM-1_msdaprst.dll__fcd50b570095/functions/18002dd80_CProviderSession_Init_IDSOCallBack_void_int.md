# CProviderSession::Init(IDSOCallBack *,void *,int)

- ea: `0x18002dd80`
- end: `0x18002def2`
- name: `?Init@CProviderSession@@QEAAJPEAUIDSOCallBack@@PEAXH@Z`
- size: `370`
- prototype: `__int64 __fastcall(CProviderSession *__hidden this, struct IDSOCallBack *, void *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180013f30`

## callees

- `0x18001a6c8`
- `0x18002cd54`
- `0x18002d770`
- `0x18002dd80`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002ddc0`
- `KERNEL32!GetCurrentThreadId` at `0x18002ddc0`
- `KERNEL32!LeaveCriticalSection` at `0x18002de90`
- `KERNEL32!LeaveCriticalSection` at `0x18002deda`
- `KERNEL32!LeaveCriticalSection` at `0x18002de90`
- `KERNEL32!LeaveCriticalSection` at `0x18002deda`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002ddec`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002ddec`
- `MSDART!UMSEnterCSWraper` at `0x18002ddac`
- `MSDART!UMSEnterCSWraper` at `0x18002ddac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProviderSession::Init(GUID *this, __int64 (***a2)(void), void *a3)
{
  GUID *v6; // rdi
  unsigned __int8 *v7; // rsi
  int v8; // eax
  unsigned int v9; // r8d
  int v10; // ebx
  bool v11; // zf
  __int64 v12; // rcx
  unsigned int v14; // ebx
  __int64 v15; // rcx
  int v16; // [rsp+30h] [rbp-58h] BYREF
  GUID *v17; // [rsp+38h] [rbp-50h]
  unsigned __int8 *v18; // [rsp+40h] [rbp-48h]
  GUID *v19; // [rsp+48h] [rbp-40h]
  GUID *v20; // [rsp+90h] [rbp+8h]
  int v21; // [rsp+A8h] [rbp+20h]

  v6 = this + 3;
  v20 = this + 3;
  UMSEnterCSWraper(&this[3]);
  v7 = &v6->Data4[4];
  v18 = &v6->Data4[4];
  if ( !*(_DWORD *)&v6->Data4[4] )
    *(_DWORD *)v6->Data4 = GetCurrentThreadId();
  ++*(_DWORD *)v7;
  v17 = v6 + 1;
  ++v6[1].Data1;
  v19 = v6;
  SetErrorInfo(0, 0);
  this[6] = IID_IDSOCallBack;
  *(_DWORD *)&this[263].Data2 = 0;
  try
  {
    v8 = (**a2)();
    v10 = v8;
    if ( v8 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180048EF8 )
          bidTraceW(off_180048230[0], 61440, off_180048EF8, (unsigned int)v8, 60);
      }
      ThrowHR(v10);
    }
    *(_QWORD *)this[282].Data4 = a3;
    this[283].Data1 = 8;
  }
  catch ( long v16 )
  {
    v21 = v16;
    goto LABEL_13;
  }
  catch ( ... )
  {
    v21 = -2147467259;
LABEL_13:
    v14 = CError::PostErrorIfNone((CError *)&this[5], v21, v9);
    --v17->Data1;
    v11 = (*(_DWORD *)v18)-- == 1;
    if ( v11 )
      *(_DWORD *)v20->Data4 = -1;
    v15 = *(_QWORD *)&v20->Data1;
    --*(_DWORD *)(v15 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
    return v14;
  }
  --v6[1].Data1;
  v11 = (*(_DWORD *)v7)-- == 1;
  if ( v11 )
    *(_DWORD *)v6->Data4 = -1;
  v12 = *(_QWORD *)&v6->Data1;
  --*(_DWORD *)(v12 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 8));
  return 0;
}

```

## disassembly

```asm
0x18002dd80  mov     [rsp+arg_18], r9d
0x18002dd85  push    rbx
0x18002dd86  push    rsi
0x18002dd87  push    rdi
0x18002dd88  push    r12
0x18002dd8a  push    r13
0x18002dd8c  push    r14
0x18002dd8e  push    r15
0x18002dd90  sub     rsp, 50h
0x18002dd94  mov     r12, r8
0x18002dd97  mov     r13, rdx
0x18002dd9a  mov     r15, rcx
0x18002dd9d  lea     rdi, [rcx+30h]
0x18002dda1  mov     [rsp+88h+arg_0], rdi
0x18002dda9  mov     rcx, rdi
0x18002ddac  call    cs:__imp_UMSEnterCSWraper
0x18002ddb2  lea     rsi, [rdi+0Ch]
0x18002ddb6  mov     [rsp+88h+var_48], rsi
0x18002ddbb  cmp     dword ptr [rsi], 0
0x18002ddbe  jnz     short loc_18002DDC9
0x18002ddc0  call    cs:__imp_GetCurrentThreadId
0x18002ddc6  mov     [rdi+8], eax
0x18002ddc9  inc     dword ptr [rsi]
0x18002ddcb  lea     r14, [rdi+10h]
0x18002ddcf  mov     [rsp+88h+var_50], r14
0x18002ddd4  inc     dword ptr [r14]
0x18002ddd7  mov     [rsp+88h+var_40], rdi
0x18002dddc  lea     rbx, [r15+50h]
0x18002dde0  mov     [rsp+88h+arg_8], rbx
0x18002dde8  xor     edx, edx; perrinfo
0x18002ddea  xor     ecx, ecx; dwReserved
0x18002ddec  call    cs:__imp_SetErrorInfo
0x18002ddf2  movups  xmm0, xmmword ptr cs:?IID_IDSOCallBack@@3U_GUID@@B.Data1; _GUID const IID_IDSOCallBack ...
0x18002ddf9  movdqu  xmmword ptr [rbx+10h], xmm0
0x18002ddfe  mov     dword ptr [rbx+1024h], 0
0x18002de08  mov     rax, [r13+0]
0x18002de0c  lea     r8, [r15+48h]
0x18002de10  lea     rdx, ?IID_IDSOCallBack@@3U_GUID@@B; _GUID const IID_IDSOCallBack
0x18002de17  mov     rcx, r13
0x18002de1a  mov     rax, [rax]
0x18002de1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de22  mov     ebx, eax
0x18002de24  test    eax, eax
0x18002de26  jns     short loc_18002DE67
0x18002de28  test    byte ptr cs:_bidGblFlags, 2
0x18002de2f  jz      short loc_18002DE60
0x18002de31  mov     rcx, cs:off_180048EF8; "<CProviderSession::Init|ADO|ERR>  HRESU"...
0x18002de38  test    rcx, rcx
0x18002de3b  jz      short loc_18002DE60
0x18002de3d  mov     [rsp+88h+var_68], 3Ch ; '<'
0x18002de45  mov     r9d, eax
0x18002de48  mov     r8, cs:off_180048EF8; "<CProviderSession::Init|ADO|ERR>  HRESU"...
0x18002de4f  mov     edx, 0F000h
0x18002de54  mov     rcx, cs:off_180048230; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002de5b  call    _bidTraceW
0x18002de60  mov     ecx, ebx; int
0x18002de62  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002de67  mov     [r15+11A8h], r12
0x18002de6e  mov     dword ptr [r15+11B0h], 8
0x18002de79  or      edx, 0FFFFFFFFh
0x18002de7c  add     [r14], edx
0x18002de7f  add     [rsi], edx
0x18002de81  jnz     short loc_18002DE86
0x18002de83  mov     [rdi+8], edx
0x18002de86  mov     rcx, [rdi]
0x18002de89  dec     dword ptr [rcx+30h]
0x18002de8c  add     rcx, 8; lpCriticalSection
0x18002de90  call    cs:__imp_LeaveCriticalSection
0x18002de96  xor     eax, eax
0x18002de98  jmp     short loc_18002DEE2
0x18002de9a  jmp     short $+2
0x18002de9c  mov     edx, [rsp+88h+arg_18]; int
0x18002dea3  mov     rcx, [rsp+88h+arg_8]; this
0x18002deab  call    ?PostErrorIfNone@CError@@QEAAJJK@Z; CError::PostErrorIfNone(long,ulong)
0x18002deb0  mov     ebx, eax
0x18002deb2  or      edx, 0FFFFFFFFh
0x18002deb5  mov     rcx, [rsp+88h+var_50]
0x18002deba  add     [rcx], edx
0x18002debc  mov     rcx, [rsp+88h+var_48]
0x18002dec1  add     [rcx], edx
0x18002dec3  mov     rcx, [rsp+88h+arg_0]
0x18002decb  jnz     short loc_18002DED0
0x18002decd  mov     [rcx+8], edx
0x18002ded0  mov     rcx, [rcx]
0x18002ded3  dec     dword ptr [rcx+30h]
0x18002ded6  add     rcx, 8; lpCriticalSection
0x18002deda  call    cs:__imp_LeaveCriticalSection
0x18002dee0  mov     eax, ebx
0x18002dee2  add     rsp, 50h
0x18002dee6  pop     r15
0x18002dee8  pop     r14
0x18002deea  pop     r13
0x18002deec  pop     r12
0x18002deee  pop     rdi
0x18002deef  pop     rsi
0x18002def0  pop     rbx
0x18002def1  retn
```
