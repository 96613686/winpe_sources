# CCachePublication::~CCachePublication(void)

- ea: `0x18008722c`
- end: `0x18008743e`
- name: `??1CCachePublication@@UEAA@XZ`
- size: `530`
- prototype: `void __fastcall(CCachePublication *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180087490`

## callees

- `0x1800024f0`
- `0x180004374`
- `0x180008290`
- `0x18000ecf4`
- `0x180018f48`
- `0x18008722c`
- `0x18008a25c`
- `0x18013937c`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008741d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008741d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800872a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800872a2`
- `KERNEL32!CancelIoEx` at `0x180087298`
- `KERNEL32!CancelIoEx` at `0x180087298`
- `KERNEL32!CloseHandle` at `0x18008738b`
- `KERNEL32!CloseHandle` at `0x18008739e`
- `KERNEL32!CloseHandle` at `0x18008738b`
- `KERNEL32!CloseHandle` at `0x18008739e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CCachePublication::~CCachePublication(CCachePublication *this)
{
  DWORD LastError; // eax
  unsigned int v3; // eax
  _QWORD *v4; // rdi
  void *v5; // rcx
  void *v6; // rcx

  *(_QWORD *)this = &CCachePublication::`vftable';
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids);
  }
  if ( *((_BYTE *)this + 1864) )
  {
    if ( !CancelIoEx(*((HANDLE *)this + 214), (LPOVERLAPPED)((char *)this + 1784)) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 11, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids, LastError);
      }
    }
    v3 = CCachePublication::WaitForPendingWrite(this);
    if ( v3
      && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 12, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids, v3);
    }
  }
  v4 = (_QWORD *)((char *)this + 88);
  if ( *((_BYTE *)this + 1777) )
  {
    (*(void (__fastcall **)(_QWORD, CCachePublication *))(*(_QWORD *)*v4 + 128LL))(*v4, this);
    *((_WORD *)this + 888) = 1;
  }
  (*(void (__fastcall **)(_QWORD, CCachePublication *))(*(_QWORD *)*v4 + 88LL))(*v4, this);
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 13, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids);
  }
  v5 = (void *)*((_QWORD *)this + 213);
  if ( v5 != (void *)-1LL )
    CloseHandle(v5);
  v6 = (void *)*((_QWORD *)this + 214);
  if ( v6 != (void *)-1LL )
    CloseHandle(v6);
  operator delete(*((void **)this + 230));
  operator delete(*((void **)this + 229));
  *((_QWORD *)this + 227) = &ObjectHandle::`vftable';
  ObjectHandle::CloseNoThrow((CCachePublication *)((char *)this + 1816));
  *((_QWORD *)this + 215) = &TnoHash::`vftable';
  TnoBaseHash::ReleaseHash((CCachePublication *)((char *)this + 1720));
  operator delete(*((void **)this + 17));
  operator delete(*((void **)this + 15));
  SmartPointer<CRepubJetSessionContext>::Release((char *)this + 88);
  SmartPointer<CRepubJetSessionContext>::Release((char *)this + 72);
  *((_QWORD *)this + 3) = &CritSec::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  *(_QWORD *)this = &ReferenceCounted::`vftable';
}

```

## disassembly

```asm
0x18008722c  mov     [rsp+arg_0], rbx
0x180087231  mov     [rsp+arg_8], rdi
0x180087236  push    r15
0x180087238  sub     rsp, 20h
0x18008723c  lea     rax, ??_7CCachePublication@@6B@; const CCachePublication::`vftable'
0x180087243  mov     rbx, rcx
0x180087246  mov     [rcx], rax
0x180087249  mov     rcx, cs:WPP_GLOBAL_Control
0x180087250  lea     r15, WPP_GLOBAL_Control
0x180087257  cmp     rcx, r15
0x18008725a  jz      short loc_18008727D
0x18008725c  test    byte ptr [rcx+6Ch], 4
0x180087260  jz      short loc_18008727D
0x180087262  cmp     byte ptr [rcx+69h], 4
0x180087266  jb      short loc_18008727D
0x180087268  mov     rcx, [rcx+60h]
0x18008726c  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x180087273  mov     edx, 0Ah
0x180087278  call    WPP_SF_
0x18008727d  cmp     byte ptr [rbx+748h], 0
0x180087284  jz      loc_180087314
0x18008728a  mov     rcx, [rbx+6B0h]; hFile
0x180087291  lea     rdx, [rbx+6F8h]; lpOverlapped
0x180087298  call    cs:__imp_CancelIoEx
0x18008729e  test    eax, eax
0x1800872a0  jnz     short loc_1800872D8
0x1800872a2  call    cs:__imp_GetLastError
0x1800872a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800872af  cmp     rcx, r15
0x1800872b2  jz      short loc_1800872D8
0x1800872b4  test    byte ptr [rcx+6Ch], 4
0x1800872b8  jz      short loc_1800872D8
0x1800872ba  cmp     byte ptr [rcx+69h], 1
0x1800872be  jb      short loc_1800872D8
0x1800872c0  mov     rcx, [rcx+60h]
0x1800872c4  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x1800872cb  mov     edx, 0Bh
0x1800872d0  mov     r9d, eax
0x1800872d3  call    WPP_SF_d
0x1800872d8  mov     rcx, rbx; this
0x1800872db  call    ?WaitForPendingWrite@CCachePublication@@AEAAKXZ; CCachePublication::WaitForPendingWrite(void)
0x1800872e0  test    eax, eax
0x1800872e2  jz      short loc_180087314
0x1800872e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800872eb  cmp     rcx, r15
0x1800872ee  jz      short loc_180087314
0x1800872f0  test    byte ptr [rcx+6Ch], 4
0x1800872f4  jz      short loc_180087314
0x1800872f6  cmp     byte ptr [rcx+69h], 1
0x1800872fa  jb      short loc_180087314
0x1800872fc  mov     rcx, [rcx+60h]
0x180087300  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x180087307  mov     edx, 0Ch
0x18008730c  mov     r9d, eax
0x18008730f  call    WPP_SF_d
0x180087314  cmp     byte ptr [rbx+6F1h], 0
0x18008731b  lea     rdi, [rbx+58h]
0x18008731f  jz      short loc_18008733F
0x180087321  mov     rcx, [rdi]
0x180087324  mov     rdx, rbx
0x180087327  mov     rax, [rcx]
0x18008732a  mov     rax, [rax+80h]
0x180087331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087336  mov     word ptr [rbx+6F0h], 1
0x18008733f  mov     rcx, [rdi]
0x180087342  mov     rdx, rbx
0x180087345  mov     rax, [rcx]
0x180087348  mov     rax, [rax+58h]
0x18008734c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087351  mov     rcx, cs:WPP_GLOBAL_Control
0x180087358  cmp     rcx, r15
0x18008735b  jz      short loc_18008737E
0x18008735d  test    byte ptr [rcx+6Ch], 4
0x180087361  jz      short loc_18008737E
0x180087363  cmp     byte ptr [rcx+69h], 4
0x180087367  jb      short loc_18008737E
0x180087369  mov     rcx, [rcx+60h]
0x18008736d  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x180087374  mov     edx, 0Dh
0x180087379  call    WPP_SF_
0x18008737e  mov     rcx, [rbx+6A8h]; hObject
0x180087385  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180087389  jz      short loc_180087391
0x18008738b  call    cs:__imp_CloseHandle
0x180087391  mov     rcx, [rbx+6B0h]; hObject
0x180087398  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008739c  jz      short loc_1800873A4
0x18008739e  call    cs:__imp_CloseHandle
0x1800873a4  mov     rcx, [rbx+730h]; Block
0x1800873ab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800873b0  mov     rcx, [rbx+728h]; Block
0x1800873b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800873bc  lea     rcx, [rbx+718h]; this
0x1800873c3  lea     rax, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x1800873ca  mov     [rcx], rax
0x1800873cd  call    ?CloseNoThrow@ObjectHandle@@IEAAKXZ; ObjectHandle::CloseNoThrow(void)
0x1800873d2  lea     rcx, [rbx+6B8h]; this
0x1800873d9  lea     rax, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x1800873e0  mov     [rcx], rax
0x1800873e3  call    ?ReleaseHash@TnoBaseHash@@QEAAXXZ; TnoBaseHash::ReleaseHash(void)
0x1800873e8  mov     rcx, [rbx+88h]; Block
0x1800873ef  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800873f4  mov     rcx, [rbx+78h]; Block
0x1800873f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800873fd  mov     rcx, rdi
0x180087400  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180087405  lea     rcx, [rbx+48h]
0x180087409  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x18008740e  lea     rax, ??_7CritSec@@6B@; const CritSec::`vftable'
0x180087415  lea     rcx, [rbx+20h]; lpCriticalSection
0x180087419  mov     [rbx+18h], rax
0x18008741d  call    cs:__imp_DeleteCriticalSection
0x180087423  mov     rdi, [rsp+28h+arg_8]
0x180087428  lea     rax, ??_7ReferenceCounted@@6B@; const ReferenceCounted::`vftable'
0x18008742f  mov     [rbx], rax
0x180087432  mov     rbx, [rsp+28h+arg_0]
0x180087437  add     rsp, 20h
0x18008743b  pop     r15
0x18008743d  retn
```
