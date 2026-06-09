# EvtIntCreateLocalLogfile

- ea: `0x1800268b0`
- end: `0x1800269c2`
- name: `EvtIntCreateLocalLogfile`
- size: `274`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180006870`
- `0x180007010`
- `0x180008924`
- `0x18000a020`
- `0x18001a71c`
- `0x180023548`
- `0x18002657c`
- `0x1800268b0`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026997`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026997`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void *__fastcall EvtIntCreateLocalLogfile(wchar_t *a1, int a2)
{
  LocalEvtxFileObject *v3; // rax
  ObjectTable *v4; // rcx
  volatile signed __int32 *v5; // rbx
  DWORD v6; // edi
  void *v7; // rbx
  EvtException *v9; // [rsp+20h] [rbp-38h] BYREF
  __int128 pExceptionObject; // [rsp+28h] [rbp-30h] BYREF
  __int64 v11; // [rsp+38h] [rbp-20h]
  int v12; // [rsp+40h] [rbp-18h]
  int v13; // [rsp+44h] [rbp-14h]
  int v14; // [rsp+48h] [rbp-10h]
  __int64 v15; // [rsp+70h] [rbp+18h] BYREF
  LocalEvtxFileObject *v16; // [rsp+78h] [rbp+20h]

  try
  {
    v15 = 0;
    if ( a2 || !a1 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
      }
      pExceptionObject = 0;
      v11 = 0;
      v12 = 87;
      v13 = -1;
      v14 = 270;
      throw (EvtException *)&pExceptionObject;
    }
    v3 = (LocalEvtxFileObject *)operator new(0x368u);
    v16 = v3;
    if ( v3 )
      v5 = (volatile signed __int32 *)LocalEvtxFileObject::LocalEvtxFileObject(v3, a1);
    else
      v5 = 0;
    if ( v5 )
      _InterlockedIncrement(v5 + 2);
    v6 = ObjectTable::AddObject(v4, (struct Object *)v5, (struct EvtHandleRef *)&v15);
    if ( v5 )
      wmi::RefBase::Release((wmi::RefBase *)v5);
  }
  catch ( EvtException *v9 )
  {
    v6 = *((_DWORD *)v9 + 6);
  }
  SetLastError(v6);
  v7 = EvtHandleRef::Detach((EvtHandleRef *)&v15);
  EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v15);
  return v7;
}

```

## disassembly

```asm
0x1800268b0  mov     [rsp+arg_0], rbx
0x1800268b5  push    rdi
0x1800268b6  sub     rsp, 50h
0x1800268ba  mov     rbx, rcx
0x1800268bd  mov     [rsp+58h+arg_10], 0
0x1800268c6  test    edx, edx
0x1800268c8  jnz     short loc_18002691D
0x1800268ca  test    rcx, rcx
0x1800268cd  jz      short loc_18002691D
0x1800268cf  mov     ecx, 368h; dwBytes
0x1800268d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800268d9  mov     [rsp+58h+arg_18], rax
0x1800268de  test    rax, rax
0x1800268e1  jz      short loc_1800268F3
0x1800268e3  mov     rdx, rbx; wchar_t *
0x1800268e6  mov     rcx, rax; this
0x1800268e9  call    ??0LocalEvtxFileObject@@QEAA@PEB_W@Z; LocalEvtxFileObject::LocalEvtxFileObject(wchar_t const *)
0x1800268ee  mov     rbx, rax
0x1800268f1  jmp     short loc_1800268F5
0x1800268f3  xor     ebx, ebx
0x1800268f5  test    rbx, rbx
0x1800268f8  jz      short loc_1800268FE
0x1800268fa  lock inc dword ptr [rbx+8]
0x1800268fe  lea     r8, [rsp+58h+arg_10]; struct EvtHandleRef *
0x180026903  mov     rdx, rbx; struct Object *
0x180026906  call    ?AddObject@ObjectTable@@QEAAKPEAVObject@@AEAVEvtHandleRef@@@Z; ObjectTable::AddObject(Object *,EvtHandleRef &)
0x18002690b  mov     edi, eax
0x18002690d  test    rbx, rbx
0x180026910  jz      short loc_18002691B
0x180026912  mov     rcx, rbx; this
0x180026915  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18002691a  nop
0x18002691b  jmp     short loc_180026995
0x18002691d  lea     rax, WPP_GLOBAL_Control
0x180026924  mov     rcx, cs:WPP_GLOBAL_Control
0x18002692b  cmp     rcx, rax
0x18002692e  jz      short loc_180026955
0x180026930  test    byte ptr [rcx+1Ch], 1
0x180026934  jz      short loc_180026955
0x180026936  cmp     byte ptr [rcx+19h], 2
0x18002693a  jb      short loc_180026955
0x18002693c  mov     edx, 0Ch
0x180026941  lea     r9d, [rdx+4Bh]
0x180026945  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x18002694c  mov     rcx, [rcx+10h]
0x180026950  call    WPP_SF_D
0x180026955  xorps   xmm0, xmm0
0x180026958  movdqu  [rsp+58h+pExceptionObject], xmm0
0x18002695e  mov     [rsp+58h+var_20], 0
0x180026967  mov     [rsp+58h+var_18], 57h ; 'W'
0x18002696f  mov     [rsp+58h+var_14], 0FFFFFFFFh
0x180026977  mov     [rsp+58h+var_10], 10Eh
0x18002697f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026986  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18002698b  call    _CxxThrowException_0
0x180026991  mov     edi, [rsp+58h+arg_8]
0x180026995  mov     ecx, edi; dwErrCode
0x180026997  call    cs:__imp_SetLastError
0x18002699d  lea     rcx, [rsp+58h+arg_10]; this
0x1800269a2  call    ?Detach@EvtHandleRef@@QEAAPEAXXZ; EvtHandleRef::Detach(void)
0x1800269a7  mov     rbx, rax
0x1800269aa  lea     rcx, [rsp+58h+arg_10]; this
0x1800269af  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x1800269b4  mov     rax, rbx
0x1800269b7  mov     rbx, [rsp+58h+arg_0]
0x1800269bc  add     rsp, 50h
0x1800269c0  pop     rdi
0x1800269c1  retn
```
