# AttributeList::~AttributeList(void)

- ea: `0x18000d4d8`
- end: `0x18000d579`
- name: `??1AttributeList@@QEAA@XZ`
- size: `161`
- prototype: `void __fastcall(AttributeList *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800037e8`
- `0x18000c854`
- `0x18000f9d8`
- `0x1800100c1`
- `0x180010f00`
- `0x18001144b`

## callees

- `0x18000d44c`
- `0x18000d4d8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000d4e9`
- `KERNEL32!CloseHandle` at `0x18000d4e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d50f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d519`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d50f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d519`

## pseudocode

```c
void __fastcall AttributeList::~AttributeList(HANDLE *this)
{
  __int64 *v2; // rbx
  void *v3; // rcx
  __int64 *i; // rax
  __int64 *v5; // rcx

  CloseHandle(this[2]);
  v2 = *(__int64 **)*this;
  while ( v2 != *this )
  {
    if ( *((_DWORD *)v2 + 10) <= 1u )
    {
      v3 = (void *)v2[6];
      if ( v3 )
        CoTaskMemFree(v3);
    }
    CoTaskMemFree((LPVOID)v2[4]);
    if ( !*((_BYTE *)v2 + 25) )
    {
      i = (__int64 *)v2[2];
      if ( *((_BYTE *)i + 25) )
      {
        for ( i = (__int64 *)v2[1]; !*((_BYTE *)i + 25) && v2 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v2 = i;
LABEL_15:
        v2 = i;
      }
      else
      {
        v5 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 25) )
          goto LABEL_15;
        do
        {
          v2 = v5;
          v5 = (__int64 *)*v5;
        }
        while ( !*((_BYTE *)v5 + 25) );
      }
    }
  }
  std::_Tree<std::_Tmap_traits<unsigned short *,Attribute,ltString,std::allocator<std::pair<unsigned short * const,Attribute>>,0>>::~_Tree<std::_Tmap_traits<unsigned short *,Attribute,ltString,std::allocator<std::pair<unsigned short * const,Attribute>>,0>>(this);
}

```

## disassembly

```asm
0x18000d4d8  mov     [rsp+arg_0], rbx
0x18000d4dd  push    rdi
0x18000d4de  sub     rsp, 20h
0x18000d4e2  mov     rdi, rcx
0x18000d4e5  mov     rcx, [rcx+10h]; hObject
0x18000d4e9  call    cs:__imp_CloseHandle
0x18000d4ef  mov     rbx, [rdi]
0x18000d4f2  mov     rbx, [rbx]
0x18000d4f5  cmp     rbx, [rdi]
0x18000d4f8  jz      short loc_18000D567
0x18000d4fa  mov     edx, [rbx+28h]
0x18000d4fd  test    edx, edx
0x18000d4ff  jz      short loc_18000D506
0x18000d501  cmp     edx, 1
0x18000d504  jnz     short loc_18000D515
0x18000d506  mov     rcx, [rbx+30h]; pv
0x18000d50a  test    rcx, rcx
0x18000d50d  jz      short loc_18000D515
0x18000d50f  call    cs:__imp_CoTaskMemFree
0x18000d515  mov     rcx, [rbx+20h]; pv
0x18000d519  call    cs:__imp_CoTaskMemFree
0x18000d51f  cmp     byte ptr [rbx+19h], 0
0x18000d523  jnz     short loc_18000D4F5
0x18000d525  mov     rax, [rbx+10h]
0x18000d529  cmp     byte ptr [rax+19h], 0
0x18000d52d  jnz     short loc_18000D549
0x18000d52f  mov     rcx, [rax]
0x18000d532  cmp     byte ptr [rcx+19h], 0
0x18000d536  jnz     short loc_18000D562
0x18000d538  mov     rax, [rcx]
0x18000d53b  mov     rbx, rcx
0x18000d53e  mov     rcx, rax
0x18000d541  cmp     byte ptr [rax+19h], 0
0x18000d545  jz      short loc_18000D538
0x18000d547  jmp     short loc_18000D4F5
0x18000d549  mov     rax, [rbx+8]
0x18000d54d  jmp     short loc_18000D55C
0x18000d54f  cmp     rbx, [rax+10h]
0x18000d553  jnz     short loc_18000D562
0x18000d555  mov     rbx, rax
0x18000d558  mov     rax, [rax+8]
0x18000d55c  cmp     byte ptr [rax+19h], 0
0x18000d560  jz      short loc_18000D54F
0x18000d562  mov     rbx, rax
0x18000d565  jmp     short loc_18000D4F5
0x18000d567  mov     rcx, rdi
0x18000d56a  mov     rbx, [rsp+28h+arg_0]
0x18000d56f  add     rsp, 20h
0x18000d573  pop     rdi
0x18000d574  jmp     ??1?$_Tree@V?$_Tmap_traits@PEAGUAttribute@@UltString@@V?$allocator@U?$pair@QEAGUAttribute@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ushort *,Attribute,ltString,std::allocator<std::pair<ushort * const,Attribute>>,0>>::~_Tree<std::_Tmap_traits<ushort *,Attribute,ltString,std::allocator<std::pair<ushort * const,Attribute>>,0>>(void)
```
