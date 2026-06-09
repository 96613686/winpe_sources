# Windows::Internal::ButtonBarLayout::DoLayout(DirectUI::Element *,int,int)

- ea: `0x18008d840`
- end: `0x18008da37`
- name: `?DoLayout@ButtonBarLayout@Internal@Windows@@UEAAXPEAVElement@DirectUI@@HH@Z`
- size: `503`
- prototype: `void __fastcall(Windows::Internal::ButtonBarLayout *__hidden this, struct DirectUI::Element *, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18005ae80`
- `0x18008d840`

## import_xrefs

- `DUI70!?IsCacheDirty@Layout@DirectUI@@IEAA_NXZ` at `0x18008d867`
- `DUI70!?IsCacheDirty@Layout@DirectUI@@IEAA_NXZ` at `0x18008d867`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18008d886`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18008d886`
- `DUI70!?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z` at `0x18008d94a`
- `DUI70!?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z` at `0x18008d995`
- `DUI70!?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z` at `0x18008d94a`
- `DUI70!?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z` at `0x18008d995`
- `DUI70!?GetLayoutChildCount@Layout@DirectUI@@QEAAIPEAVElement@2@@Z` at `0x18008d897`
- `DUI70!?GetLayoutChildCount@Layout@DirectUI@@QEAAIPEAVElement@2@@Z` at `0x18008d897`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18008d97b`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18008d9c6`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18008d97b`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18008d9c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Internal::ButtonBarLayout::DoLayout(
        Windows::Internal::ButtonBarLayout *this,
        struct DirectUI::Element *a2,
        int a3,
        int a4)
{
  unsigned int LayoutChildCount; // r9d
  char v8; // r8
  int v9; // edi
  int v10; // esi
  int v11; // eax
  int v12; // edx
  int v13; // ecx
  int v14; // r12d
  __int64 v15; // r15
  __int64 v16; // rbp
  struct DirectUI::Element *ChildFromLayoutIndex; // rax
  struct DirectUI::Element *v18; // rax
  int v19; // [rsp+40h] [rbp-58h]
  int v20; // [rsp+44h] [rbp-54h]
  unsigned int v21; // [rsp+48h] [rbp-50h]
  __int64 Children; // [rsp+50h] [rbp-48h]
  _QWORD v23[8]; // [rsp+58h] [rbp-40h] BYREF

  if ( !DirectUI::Layout::IsCacheDirty(this) )
  {
    v23[0] = 0;
    Children = DirectUI::Element::GetChildren(a2, v23);
    LayoutChildCount = DirectUI::Layout::GetLayoutChildCount(this, a2);
    if ( LayoutChildCount )
    {
      v8 = *((_BYTE *)this + 272);
      v9 = a3 - *(_DWORD *)((char *)this + (v8 != 0 ? 4 : 0) + 276);
      v10 = a3;
      if ( *((_DWORD *)this + 70) < a3 )
        v10 = *((_DWORD *)this + 70);
      if ( v9 < 0 )
      {
        v8 = 1;
        *((_BYTE *)this + 272) = 1;
        v11 = 0;
        if ( v10 >= 0 )
          v11 = v10;
        v10 = v11;
        v9 = a3 - v11;
      }
      v21 = LayoutChildCount - 1;
      if ( LayoutChildCount != 1 )
      {
        v12 = 0;
        v19 = 0;
        v13 = 0;
        v20 = 0;
        v14 = 0;
        v15 = 0;
        do
        {
          v16 = 8 * ((unsigned int)v15 + 2 * v15);
          if ( v8 )
          {
            v14 += v13;
          }
          else
          {
            v9 += v12;
            v10 = *(_DWORD *)((char *)this + v16 + 32);
          }
          ChildFromLayoutIndex = (struct DirectUI::Element *)DirectUI::Layout::GetChildFromLayoutIndex(
                                                               this,
                                                               a2,
                                                               (unsigned int)v15,
                                                               Children);
          DirectUI::Layout::UpdateLayoutRect(
            a2,
            a3,
            a4,
            ChildFromLayoutIndex,
            v9,
            v14,
            v10,
            *(_DWORD *)((char *)this + v16 + 36));
          v18 = (struct DirectUI::Element *)DirectUI::Layout::GetChildFromLayoutIndex(
                                              this,
                                              a2,
                                              (unsigned int)(v15 + 1),
                                              Children);
          DirectUI::Layout::UpdateLayoutRect(a2, a3, a4, v18, v9, v14, v10, *(_DWORD *)((char *)this + v16 + 36));
          v8 = *((_BYTE *)this + 272);
          if ( v8 )
          {
            v14 += *(_DWORD *)((char *)this + v16 + 36);
            v13 = *(_DWORD *)((char *)this + v16 + 52);
            v20 = v13;
            v12 = v19;
          }
          else
          {
            v9 += *(_DWORD *)((char *)this + v16 + 32);
            v12 = *((_DWORD *)this + 4 * v15 + 2 * (unsigned int)v15 + 12);
            v19 = v12;
            v13 = v20;
          }
          v15 = (unsigned int)(v15 + 2);
        }
        while ( (unsigned int)v15 < v21 );
      }
    }
    CValuePtr::Release((CValuePtr *)v23);
  }
}

```

## disassembly

```asm
0x18008d840  mov     [rsp+arg_0], rbx
0x18008d845  mov     [rsp+arg_18], r9d
0x18008d84a  mov     [rsp+arg_8], rdx
0x18008d84f  push    rbp
0x18008d850  push    rsi
0x18008d851  push    rdi
0x18008d852  push    r12
0x18008d854  push    r13
0x18008d856  push    r14
0x18008d858  push    r15
0x18008d85a  sub     rsp, 60h
0x18008d85e  mov     r14d, r8d
0x18008d861  mov     rdi, rdx
0x18008d864  mov     rbx, rcx
0x18008d867  call    cs:__imp_?IsCacheDirty@Layout@DirectUI@@IEAA_NXZ; DirectUI::Layout::IsCacheDirty(void)
0x18008d86d  test    al, al
0x18008d86f  jnz     loc_18008DA1F
0x18008d875  mov     [rsp+98h+var_40], 0
0x18008d87e  lea     rdx, [rsp+98h+var_40]
0x18008d883  mov     rcx, rdi
0x18008d886  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x18008d88c  mov     [rsp+98h+var_48], rax
0x18008d891  mov     rdx, rdi
0x18008d894  mov     rcx, rbx
0x18008d897  call    cs:__imp_?GetLayoutChildCount@Layout@DirectUI@@QEAAIPEAVElement@2@@Z; DirectUI::Layout::GetLayoutChildCount(DirectUI::Element *)
0x18008d89d  mov     r9d, eax
0x18008d8a0  test    eax, eax
0x18008d8a2  jz      loc_18008DA15
0x18008d8a8  mov     r8b, [rbx+110h]
0x18008d8af  mov     cl, r8b
0x18008d8b2  neg     cl
0x18008d8b4  sbb     rdx, rdx
0x18008d8b7  and     edx, 4
0x18008d8ba  mov     edi, r14d
0x18008d8bd  sub     edi, [rdx+rbx+114h]
0x18008d8c4  mov     ecx, [rbx+118h]
0x18008d8ca  mov     esi, r14d
0x18008d8cd  cmp     ecx, r14d
0x18008d8d0  cmovl   esi, ecx
0x18008d8d3  test    edi, edi
0x18008d8d5  jns     short loc_18008D8EF
0x18008d8d7  mov     r8b, 1
0x18008d8da  mov     [rbx+110h], r8b
0x18008d8e1  xor     eax, eax
0x18008d8e3  test    esi, esi
0x18008d8e5  cmovns  eax, esi
0x18008d8e8  mov     esi, eax
0x18008d8ea  mov     edi, r14d
0x18008d8ed  sub     edi, eax
0x18008d8ef  lea     eax, [r9-1]
0x18008d8f3  mov     [rsp+98h+var_50], eax
0x18008d8f7  test    eax, eax
0x18008d8f9  jz      loc_18008DA15
0x18008d8ff  xor     edx, edx
0x18008d901  mov     [rsp+98h+var_58], edx
0x18008d905  xor     ecx, ecx
0x18008d907  mov     [rsp+98h+var_54], ecx
0x18008d90b  xor     r12d, r12d
0x18008d90e  xor     r15d, r15d
0x18008d911  mov     r13d, r15d
0x18008d914  lea     rax, ds:0[r15*2]
0x18008d91c  add     rax, r13
0x18008d91f  lea     rbp, ds:0[rax*8]
0x18008d927  test    r8b, r8b
0x18008d92a  jz      short loc_18008D931
0x18008d92c  add     r12d, ecx
0x18008d92f  jmp     short loc_18008D937
0x18008d931  add     edi, edx
0x18008d933  mov     esi, [rbx+rbp+20h]
0x18008d937  mov     r9, [rsp+98h+var_48]
0x18008d93c  mov     r8d, r15d
0x18008d93f  mov     rdx, [rsp+98h+arg_8]
0x18008d947  mov     rcx, rbx
0x18008d94a  call    cs:__imp_?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z; DirectUI::Layout::GetChildFromLayoutIndex(DirectUI::Element *,int,DirectUI::DynamicArray<DirectUI::Element *,0> *)
0x18008d950  mov     ecx, [rbx+rbp+24h]
0x18008d954  mov     [rsp+98h+var_60], ecx
0x18008d958  mov     [rsp+98h+var_68], esi
0x18008d95c  mov     [rsp+98h+var_70], r12d
0x18008d961  mov     [rsp+98h+var_78], edi
0x18008d965  mov     r9, rax
0x18008d968  mov     r8d, [rsp+98h+arg_18]
0x18008d970  mov     edx, r14d
0x18008d973  mov     rcx, [rsp+98h+arg_8]
0x18008d97b  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x18008d981  lea     r8d, [r15+1]
0x18008d985  mov     r9, [rsp+98h+var_48]
0x18008d98a  mov     rdx, [rsp+98h+arg_8]
0x18008d992  mov     rcx, rbx
0x18008d995  call    cs:__imp_?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z; DirectUI::Layout::GetChildFromLayoutIndex(DirectUI::Element *,int,DirectUI::DynamicArray<DirectUI::Element *,0> *)
0x18008d99b  mov     ecx, [rbx+rbp+24h]
0x18008d99f  mov     [rsp+98h+var_60], ecx
0x18008d9a3  mov     [rsp+98h+var_68], esi
0x18008d9a7  mov     [rsp+98h+var_70], r12d
0x18008d9ac  mov     [rsp+98h+var_78], edi
0x18008d9b0  mov     r9, rax
0x18008d9b3  mov     r8d, [rsp+98h+arg_18]
0x18008d9bb  mov     edx, r14d
0x18008d9be  mov     rcx, [rsp+98h+arg_8]
0x18008d9c6  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x18008d9cc  mov     r8b, [rbx+110h]
0x18008d9d3  test    r8b, r8b
0x18008d9d6  jz      short loc_18008D9EB
0x18008d9d8  add     r12d, [rbx+rbp+24h]
0x18008d9dd  mov     ecx, [rbx+rbp+34h]
0x18008d9e1  mov     [rsp+98h+var_54], ecx
0x18008d9e5  mov     edx, [rsp+98h+var_58]
0x18008d9e9  jmp     short loc_18008DA06
0x18008d9eb  add     edi, [rbx+rbp+20h]
0x18008d9ef  lea     rax, ds:0[r15*2]
0x18008d9f7  add     rax, r13
0x18008d9fa  mov     edx, [rbx+rax*8+30h]
0x18008d9fe  mov     [rsp+98h+var_58], edx
0x18008da02  mov     ecx, [rsp+98h+var_54]
0x18008da06  add     r15d, 2
0x18008da0a  cmp     r15d, [rsp+98h+var_50]
0x18008da0f  jb      loc_18008D911
0x18008da15  lea     rcx, [rsp+98h+var_40]; this
0x18008da1a  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x18008da1f  mov     rbx, [rsp+98h+arg_0]
0x18008da27  add     rsp, 60h
0x18008da2b  pop     r15
0x18008da2d  pop     r14
0x18008da2f  pop     r13
0x18008da31  pop     r12
0x18008da33  pop     rdi
0x18008da34  pop     rsi
0x18008da35  pop     rbp
0x18008da36  retn
```
