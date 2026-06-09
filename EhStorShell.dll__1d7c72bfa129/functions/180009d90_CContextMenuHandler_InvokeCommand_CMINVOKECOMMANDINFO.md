# CContextMenuHandler::InvokeCommand(_CMINVOKECOMMANDINFO *)

- ea: `0x180009d90`
- end: `0x180009eec`
- name: `?InvokeCommand@CContextMenuHandler@@UEAAJPEAU_CMINVOKECOMMANDINFO@@@Z`
- size: `348`
- prototype: `__int64 __fastcall(CContextMenuHandler *this, struct _CMINVOKECOMMANDINFO *, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000684c`
- `0x180009b44`
- `0x180009d90`
- `0x18000a354`
- `0x18000a428`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CContextMenuHandler::InvokeCommand(
        CContextMenuHandler *this,
        struct _CMINVOKECOMMANDINFO *a2,
        __int64 a3,
        __int64 a4)
{
  PVOID *v6; // rcx
  unsigned __int64 lpVerb_low; // rbx
  void (*v8)(void); // rax

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, WORD1(a2->lpVerb), LOWORD(a2->lpVerb));
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !WORD1(a2->lpVerb) )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
    {
      WPP_SF_dd(
        v6[2],
        34,
        &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids,
        LOWORD(a2->lpVerb),
        *((_DWORD *)this + 10) + 1);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    lpVerb_low = LOWORD(a2->lpVerb);
    if ( lpVerb_low <= *((_QWORD *)this + 5) + 1LL )
    {
      if ( (_DWORD)lpVerb_low == 1 )
      {
        if ( !*((_DWORD *)this + 17) )
        {
          if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
            WPP_SF_(v6[2], 35, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, a4);
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 3) + 24LL))(*((_QWORD *)this + 3), 0, 0);
          return 0;
        }
        if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
          WPP_SF_(v6[2], 36, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, a4);
        v8 = *(void (**)(void))(**((_QWORD **)this + 3) + 32LL);
      }
      else
      {
        if ( (unsigned int)lpVerb_low < 2 )
          return 0;
        if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
          WPP_SF_(v6[2], 37, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, a4);
        v8 = *(void (**)(void))(**(_QWORD **)ATL::CAtlArray<IEnhancedStorageSiloAction *,ATL::CElementTraits<IEnhancedStorageSiloAction *>>::operator[](
                                               (char *)this + 32,
                                               (unsigned int)(lpVerb_low - 2))
                              + 40LL);
      }
      v8();
      return 0;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180009d90  push    rbx
0x180009d92  push    rbp
0x180009d93  push    rdi
0x180009d94  push    r15
0x180009d96  sub     rsp, 38h
0x180009d9a  mov     rbx, rdx
0x180009d9d  mov     rdi, rcx
0x180009da0  mov     rcx, cs:WPP_GLOBAL_Control
0x180009da7  lea     rbp, WPP_GLOBAL_Control
0x180009dae  cmp     rcx, rbp
0x180009db1  jz      short loc_180009DD6
0x180009db3  test    byte ptr [rcx+1Ch], 20h
0x180009db7  jz      short loc_180009DD6
0x180009db9  movzx   eax, word ptr [rdx+10h]
0x180009dbd  movzx   r9d, word ptr [rdx+12h]
0x180009dc2  mov     rcx, [rcx+10h]
0x180009dc6  mov     [rsp+58h+var_38], eax
0x180009dca  call    WPP_SF_DD
0x180009dcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180009dd6  xor     r15d, r15d
0x180009dd9  cmp     [rbx+12h], r15w
0x180009dde  jnz     loc_180009EDD
0x180009de4  cmp     rcx, rbp
0x180009de7  jz      short loc_180009E18
0x180009de9  test    byte ptr [rcx+1Ch], 20h
0x180009ded  jz      short loc_180009E18
0x180009def  mov     eax, [rdi+28h]
0x180009df2  lea     edx, [r15+22h]
0x180009df6  movzx   r9d, word ptr [rbx+10h]
0x180009dfb  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x180009e02  mov     rcx, [rcx+10h]
0x180009e06  inc     eax
0x180009e08  mov     [rsp+58h+var_38], eax
0x180009e0c  call    WPP_SF_dd
0x180009e11  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e18  mov     rax, [rdi+28h]
0x180009e1c  movzx   ebx, word ptr [rbx+10h]
0x180009e20  inc     rax
0x180009e23  cmp     rbx, rax
0x180009e26  ja      loc_180009EDD
0x180009e2c  cmp     ebx, 1
0x180009e2f  jnz     short loc_180009E99
0x180009e31  cmp     [rdi+44h], r15d
0x180009e35  jnz     short loc_180009E6C
0x180009e37  cmp     rcx, rbp
0x180009e3a  jz      short loc_180009E55
0x180009e3c  test    byte ptr [rcx+1Ch], 20h
0x180009e40  jz      short loc_180009E55
0x180009e42  mov     rcx, [rcx+10h]
0x180009e46  lea     edx, [rbx+22h]
0x180009e49  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x180009e50  call    WPP_SF_
0x180009e55  mov     rcx, [rdi+18h]
0x180009e59  xor     r8d, r8d
0x180009e5c  xor     edx, edx
0x180009e5e  mov     rax, [rcx]
0x180009e61  mov     rax, [rax+18h]
0x180009e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e6a  jmp     short loc_180009ED9
0x180009e6c  cmp     rcx, rbp
0x180009e6f  jz      short loc_180009E8C
0x180009e71  test    byte ptr [rcx+1Ch], 20h
0x180009e75  jz      short loc_180009E8C
0x180009e77  mov     rcx, [rcx+10h]
0x180009e7b  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x180009e82  mov     edx, 24h ; '$'
0x180009e87  call    WPP_SF_
0x180009e8c  mov     rcx, [rdi+18h]
0x180009e90  mov     rax, [rcx]
0x180009e93  mov     rax, [rax+20h]
0x180009e97  jmp     short loc_180009ED4
0x180009e99  cmp     ebx, 2
0x180009e9c  jb      short loc_180009ED9
0x180009e9e  cmp     rcx, rbp
0x180009ea1  jz      short loc_180009EBE
0x180009ea3  test    byte ptr [rcx+1Ch], 20h
0x180009ea7  jz      short loc_180009EBE
0x180009ea9  mov     rcx, [rcx+10h]
0x180009ead  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x180009eb4  mov     edx, 25h ; '%'
0x180009eb9  call    WPP_SF_
0x180009ebe  lea     edx, [rbx-2]
0x180009ec1  lea     rcx, [rdi+20h]
0x180009ec5  call    ??A?$CAtlArray@PEAUIEnhancedStorageSiloAction@@V?$CElementTraits@PEAUIEnhancedStorageSiloAction@@@ATL@@@ATL@@QEAAAEAPEAUIEnhancedStorageSiloAction@@_K@Z; ATL::CAtlArray<IEnhancedStorageSiloAction *,ATL::CElementTraits<IEnhancedStorageSiloAction *>>::operator[](unsigned __int64)
0x180009eca  mov     rcx, [rax]
0x180009ecd  mov     rax, [rcx]
0x180009ed0  mov     rax, [rax+28h]
0x180009ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ed9  xor     eax, eax
0x180009edb  jmp     short loc_180009EE2
0x180009edd  mov     eax, 80070057h
0x180009ee2  add     rsp, 38h
0x180009ee6  pop     r15
0x180009ee8  pop     rdi
0x180009ee9  pop     rbp
0x180009eea  pop     rbx
0x180009eeb  retn
```
