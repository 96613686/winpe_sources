# _DUI_PaintElementTreeWorker

- ea: `0x1800aeaa4`
- end: `0x1800aec93`
- name: `_DUI_PaintElementTreeWorker`
- size: `495`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800ae4e0`
- `0x1800aeaa4`

## callees

- `0x180015fe0`
- `0x180016790`
- `0x1800aeaa4`
- `0x18013f7d0`
- `0x180210010`

## import_xrefs

- `USER32!IntersectRect` at `0x1800aeb58`
- `USER32!IntersectRect` at `0x1800aeb58`
- `USER32!IsRectEmpty` at `0x1800aeb62`
- `USER32!IsRectEmpty` at `0x1800aeb74`
- `USER32!IsRectEmpty` at `0x1800aeb62`
- `USER32!IsRectEmpty` at `0x1800aeb74`
- `USER32!SetRect` at `0x1800aeb40`
- `USER32!SetRect` at `0x1800aeb40`
- `DUI70!?GetLocation@Element@DirectUI@@QEAAPEBUtagPOINT@@PEAPEAVValue@2@@Z` at `0x1800aebfc`
- `DUI70!?GetLocation@Element@DirectUI@@QEAAPEBUtagPOINT@@PEAPEAVValue@2@@Z` at `0x1800aebfc`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800aec53`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800aec62`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800aec53`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800aec62`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x1800aeb04`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x1800aeb04`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x1800aebb0`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x1800aebb0`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800aeaf4`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800aeaf4`
- `DUI70!?VisibleProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800aeaea`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall DUI_PaintElementTreeWorker(__int64 a1, int *a2, RECT *a3, DirectUI::Element *a4)
{
  DirectUI::Value *Value; // r15
  struct tagSIZE ElementExtent; // rax
  _DWORD *Children; // rax
  _DWORD *v11; // r14
  bool v12; // zf
  unsigned int v13; // r13d
  unsigned int v14; // r15d
  _DWORD *v15; // rsi
  DirectUI::Element *v16; // rsi
  const struct tagPOINT *Location; // rax
  LONG y; // edi
  LONG x; // ebx
  DirectUI::Value *v20; // rcx
  struct DirectUI::Value *v21; // [rsp+40h] [rbp-49h] BYREF
  DirectUI::Value *v22; // [rsp+48h] [rbp-41h] BYREF
  _DWORD v23[2]; // [rsp+50h] [rbp-39h] BYREF
  int *v24; // [rsp+58h] [rbp-31h]
  RECT *lprcSrc2; // [rsp+60h] [rbp-29h]
  __int64 v26; // [rsp+68h] [rbp-21h]
  DirectUI::Value *v27; // [rsp+70h] [rbp-19h]
  struct tagRECT rc; // [rsp+78h] [rbp-11h] BYREF
  struct tagRECT rcDst; // [rsp+88h] [rbp-1h] BYREF

  lprcSrc2 = a3;
  v24 = a2;
  v26 = a1;
  Value = DirectUI::Element::GetValue(
            a4,
            (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::VisibleProp,
            2,
            0);
  v27 = Value;
  if ( DirectUI::Value::GetBool(Value) )
  {
    ElementExtent = DUI_GetElementExtent(a4);
    rc = 0;
    SetRect(&rc, *a2, a2[1], *a2 + ElementExtent.cx, a2[1] + ElementExtent.cy);
    rcDst = 0;
    IntersectRect(&rcDst, &rc, a3);
    if ( !IsRectEmpty(&rc) && !IsRectEmpty(&rcDst) )
    {
      (*(void (__fastcall **)(DirectUI::Element *, __int64, struct tagRECT *, RECT *, _QWORD, _QWORD))(*(_QWORD *)a4 + 112LL))(
        a4,
        a1,
        &rc,
        a3,
        0,
        0);
      v22 = 0;
      Children = (_DWORD *)DirectUI::Element::GetChildren(a4, &v22);
      v11 = Children;
      if ( Children )
      {
        v12 = (*Children & 0xFFFFFFF) == 0;
        v13 = *Children & 0xFFFFFFF;
        LODWORD(v21) = 0;
        if ( !v12 )
        {
          v14 = 0;
          do
          {
            if ( (*v11 & 0x10000000) != 0 )
              v15 = (_DWORD *)*((_QWORD *)v11 + 1);
            else
              v15 = v11 + 2;
            v16 = *(DirectUI::Element **)&v15[2 * v14];
            v21 = 0;
            Location = DirectUI::Element::GetLocation(v16, &v21);
            y = Location->y;
            x = Location->x;
            CValuePtr::~CValuePtr((CValuePtr *)&v21);
            v23[0] = x + *v24;
            v23[1] = y + v24[1];
            DUI_PaintElementTreeWorker(v26, v23, lprcSrc2, v16);
            ++v14;
          }
          while ( v14 < v13 );
          Value = v27;
        }
      }
      v20 = v22;
      if ( v22 )
      {
        v22 = 0;
        DirectUI::Value::Release(v20);
      }
    }
  }
  if ( Value )
    DirectUI::Value::Release(Value);
}

```

## disassembly

```asm
0x1800aeaa4  push    rbp
0x1800aeaa6  push    rbx
0x1800aeaa7  push    rsi
0x1800aeaa8  push    rdi
0x1800aeaa9  push    r12
0x1800aeaab  push    r13
0x1800aeaad  push    r14
0x1800aeaaf  push    r15
0x1800aeab1  lea     rbp, [rsp-1Fh]
0x1800aeab6  sub     rsp, 0A8h
0x1800aeabd  mov     rax, cs:__security_cookie
0x1800aeac4  xor     rax, rsp
0x1800aeac7  mov     [rbp+57h+var_48], rax
0x1800aeacb  mov     rbx, r9
0x1800aeace  mov     rdi, r8
0x1800aead1  mov     [rbp+57h+lprcSrc2], r8
0x1800aead5  mov     rsi, rdx
0x1800aead8  mov     [rbp+57h+var_88], rdx
0x1800aeadc  mov     r14, rcx
0x1800aeadf  mov     [rbp+57h+var_78], rcx
0x1800aeae3  xor     r9d, r9d
0x1800aeae6  lea     r8d, [r9+2]
0x1800aeaea  mov     rdx, cs:__imp_?VisibleProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::VisibleProp(void)
0x1800aeaf1  mov     rcx, rbx
0x1800aeaf4  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800aeafa  mov     r15, rax
0x1800aeafd  mov     [rbp+57h+var_70], rax
0x1800aeb01  mov     rcx, rax
0x1800aeb04  call    cs:__imp_?GetBool@Value@DirectUI@@QEAA_NXZ; DirectUI::Value::GetBool(void)
0x1800aeb0a  xor     r12d, r12d
0x1800aeb0d  test    al, al
0x1800aeb0f  jz      loc_1800AEC5A
0x1800aeb15  mov     rcx, rbx; struct DirectUI::Element *
0x1800aeb18  call    ?DUI_GetElementExtent@@YA?AUtagSIZE@@PEAVElement@DirectUI@@@Z; DUI_GetElementExtent(DirectUI::Element *)
0x1800aeb1d  xorps   xmm0, xmm0
0x1800aeb20  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x1800aeb24  mov     r8d, [rsi+4]; yTop
0x1800aeb28  mov     edx, [rsi]; xLeft
0x1800aeb2a  mov     rcx, rax
0x1800aeb2d  shr     rcx, 20h
0x1800aeb31  add     ecx, r8d
0x1800aeb34  lea     r9d, [rdx+rax]; xRight
0x1800aeb38  mov     [rsp+0E0h+yBottom], ecx; yBottom
0x1800aeb3c  lea     rcx, [rbp+57h+rc]; lprc
0x1800aeb40  call    cs:__imp_SetRect
0x1800aeb46  xorps   xmm0, xmm0
0x1800aeb49  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x1800aeb4d  mov     r8, rdi; lprcSrc2
0x1800aeb50  lea     rdx, [rbp+57h+rc]; lprcSrc1
0x1800aeb54  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x1800aeb58  call    cs:__imp_IntersectRect
0x1800aeb5e  lea     rcx, [rbp+57h+rc]; lprc
0x1800aeb62  call    cs:__imp_IsRectEmpty
0x1800aeb68  test    eax, eax
0x1800aeb6a  jnz     loc_1800AEC5A
0x1800aeb70  lea     rcx, [rbp+57h+rcDst]; lprc
0x1800aeb74  call    cs:__imp_IsRectEmpty
0x1800aeb7a  test    eax, eax
0x1800aeb7c  jnz     loc_1800AEC5A
0x1800aeb82  mov     rax, [rbx]
0x1800aeb85  mov     [rsp+0E0h+var_B8], r12
0x1800aeb8a  mov     qword ptr [rsp+0E0h+yBottom], r12
0x1800aeb8f  mov     r9, rdi
0x1800aeb92  lea     r8, [rbp+57h+rc]
0x1800aeb96  mov     rdx, r14
0x1800aeb99  mov     rcx, rbx
0x1800aeb9c  mov     rax, [rax+70h]
0x1800aeba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeba5  mov     [rbp+57h+var_98], r12
0x1800aeba9  lea     rdx, [rbp+57h+var_98]
0x1800aebad  mov     rcx, rbx
0x1800aebb0  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x1800aebb6  mov     r14, rax
0x1800aebb9  test    rax, rax
0x1800aebbc  jz      loc_1800AEC46
0x1800aebc2  mov     r13d, [rax]
0x1800aebc5  and     r13d, 0FFFFFFFh
0x1800aebcc  mov     dword ptr [rbp+57h+var_A0], r12d
0x1800aebd0  jbe     short loc_1800AEC46
0x1800aebd2  mov     r15d, r12d
0x1800aebd5  test    dword ptr [r14], 10000000h
0x1800aebdc  jz      loc_1800AEC89
0x1800aebe2  mov     rsi, [r14+8]
0x1800aebe6  mov     eax, r15d
0x1800aebe9  mov     rsi, [rsi+rax*8]
0x1800aebed  mov     [rbp+57h+var_A0], 0
0x1800aebf5  lea     rdx, [rbp+57h+var_A0]
0x1800aebf9  mov     rcx, rsi
0x1800aebfc  call    cs:__imp_?GetLocation@Element@DirectUI@@QEAAPEBUtagPOINT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetLocation(DirectUI::Value * *)
0x1800aec02  mov     edi, [rax+4]
0x1800aec05  mov     ebx, [rax]
0x1800aec07  lea     rcx, [rbp+57h+var_A0]; this
0x1800aec0b  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x1800aec10  mov     rdx, [rbp+57h+var_88]
0x1800aec14  mov     ecx, [rdx]
0x1800aec16  add     ecx, ebx
0x1800aec18  mov     [rbp+57h+var_90], ecx
0x1800aec1b  mov     ecx, [rdx+4]
0x1800aec1e  add     ecx, edi
0x1800aec20  mov     [rbp+57h+var_8C], ecx
0x1800aec23  mov     r9, rsi
0x1800aec26  mov     r8, [rbp+57h+lprcSrc2]
0x1800aec2a  lea     rdx, [rbp+57h+var_90]
0x1800aec2e  mov     rcx, [rbp+57h+var_78]
0x1800aec32  call    _DUI_PaintElementTreeWorker
0x1800aec37  inc     r15d
0x1800aec3a  cmp     r15d, r13d
0x1800aec3d  jb      short loc_1800AEBD5
0x1800aec3f  mov     r15, [rbp+57h+var_70]
0x1800aec43  xor     r12d, r12d
0x1800aec46  mov     rcx, [rbp+57h+var_98]
0x1800aec4a  test    rcx, rcx
0x1800aec4d  jz      short loc_1800AEC5A
0x1800aec4f  mov     [rbp+57h+var_98], r12
0x1800aec53  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800aec59  nop
0x1800aec5a  test    r15, r15
0x1800aec5d  jz      short loc_1800AEC69
0x1800aec5f  mov     rcx, r15
0x1800aec62  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800aec68  nop
0x1800aec69  mov     rcx, [rbp+57h+var_48]
0x1800aec6d  xor     rcx, rsp; StackCookie
0x1800aec70  call    __security_check_cookie
0x1800aec75  add     rsp, 0A8h
0x1800aec7c  pop     r15
0x1800aec7e  pop     r14
0x1800aec80  pop     r13
0x1800aec82  pop     r12
0x1800aec84  pop     rdi
0x1800aec85  pop     rsi
0x1800aec86  pop     rbx
0x1800aec87  pop     rbp
0x1800aec88  retn
0x1800aec89  lea     rsi, [r14+8]
0x1800aec8d  jmp     loc_1800AEBE6
```
