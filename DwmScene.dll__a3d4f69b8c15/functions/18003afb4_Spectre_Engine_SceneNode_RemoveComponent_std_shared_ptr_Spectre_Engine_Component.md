# Spectre::Engine::SceneNode::RemoveComponent(std::shared_ptr<Spectre::Engine::Component>)

- ea: `0x18003afb4`
- end: `0x18003b0d0`
- name: `?RemoveComponent@SceneNode@Engine@Spectre@@QEAAXV?$shared_ptr@VComponent@Engine@Spectre@@@std@@@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001557c`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x1800311c0`
- `0x180038a38`
- `0x18003afb4`
- `0x18003bf44`
- `0x1800681a8`
- `0x1800e7010`

## string_xrefs

- `0x18003b00a`: `Attempt to remove component that has not been added to scene node.`
- `0x18003b01c`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scenenode.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Spectre::Engine::SceneNode::RemoveComponent(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rdx
  _QWORD *v5; // r8
  _QWORD *v6; // rcx
  int v7; // eax
  int v8; // r8d
  std::_Ref_count_base *v9; // rcx
  _BYTE v10[32]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v11[32]; // [rsp+60h] [rbp-68h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+80h] [rbp-48h] BYREF

  Spectre::Engine::SceneNode::VerifyWriteAccess((Spectre::Engine::SceneNode *)a1);
  v4 = *(_QWORD **)(a1 + 384);
  v5 = *(_QWORD **)(a1 + 376);
  if ( v5 == v4 )
  {
LABEL_4:
    std::string::string(v11, "Attempt to remove component that has not been added to scene node.");
    v7 = std::string::string(
           v10,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scenenode.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v7, v8, (unsigned int)v11, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  while ( 1 )
  {
    v6 = v5 + 2;
    if ( *v5 == *a2 )
      break;
    v5 += 2;
    if ( v6 == v4 )
      goto LABEL_4;
  }
  std::_Move_unchecked<std::shared_ptr<Spectre::Engine::ImageProcessingEffect> *,std::shared_ptr<Spectre::Engine::ImageProcessingEffect> *>(v6);
  std::shared_ptr<Spectre::Engine::Camera>::`scalar deleting destructor'(*(_QWORD *)(a1 + 384) - 16LL);
  *(_QWORD *)(a1 + 384) -= 16LL;
  if ( *(_BYTE *)(a1 + 104) )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 128LL))(*a2);
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 112LL))(*a2);
  v9 = (std::_Ref_count_base *)a2[1];
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
}

```

## disassembly

```asm
0x18003afb4  mov     [rsp+arg_10], rbx
0x18003afb9  push    rdi
0x18003afba  sub     rsp, 0C0h
0x18003afc1  mov     rax, cs:__security_cookie
0x18003afc8  xor     rax, rsp
0x18003afcb  mov     [rsp+0C8h+var_10], rax
0x18003afd3  mov     rbx, rdx
0x18003afd6  mov     rdi, rcx
0x18003afd9  mov     [rsp+0C8h+var_98], rdx
0x18003afde  call    ?VerifyWriteAccess@SceneNode@Engine@Spectre@@QEBAXXZ; Spectre::Engine::SceneNode::VerifyWriteAccess(void)
0x18003afe3  mov     rdx, [rdi+180h]
0x18003afea  mov     r8, [rdi+178h]
0x18003aff1  cmp     r8, rdx
0x18003aff4  jz      short loc_18003B00A
0x18003aff6  mov     rax, [rbx]
0x18003aff9  lea     rcx, [r8+10h]
0x18003affd  cmp     [r8], rax
0x18003b000  jz      short loc_18003B05C
0x18003b002  mov     r8, rcx
0x18003b005  cmp     rcx, rdx
0x18003b008  jnz     short loc_18003AFF9
0x18003b00a  lea     rdx, aAttemptToRemov; "Attempt to remove component that has no"...
0x18003b011  lea     rcx, [rsp+0C8h+var_68]
0x18003b016  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003b01b  nop
0x18003b01c  lea     rdx, aOnecoreuapWind_43; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003b023  lea     rcx, [rsp+0C8h+var_88]
0x18003b028  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003b02d  mov     [rsp+0C8h+var_A8], 0
0x18003b032  lea     r9, [rsp+0C8h+var_68]
0x18003b037  mov     rdx, rax
0x18003b03a  lea     rcx, [rsp+0C8h+pExceptionObject]
0x18003b042  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x18003b047  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x18003b04e  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18003b056  call    _CxxThrowException_0
0x18003b05c  call    ??$_Move_unchecked@PEAV?$shared_ptr@VImageProcessingEffect@Engine@Spectre@@@std@@PEAV12@@std@@YAPEAV?$shared_ptr@VImageProcessingEffect@Engine@Spectre@@@0@PEAV10@00@Z; std::_Move_unchecked<std::shared_ptr<Spectre::Engine::ImageProcessingEffect> *,std::shared_ptr<Spectre::Engine::ImageProcessingEffect> *>(std::shared_ptr<Spectre::Engine::ImageProcessingEffect> *,std::shared_ptr<Spectre::Engine::ImageProcessingEffect> *,std::shared_ptr<Spectre::Engine::ImageProcessingEffect> *)
0x18003b061  mov     rcx, [rdi+180h]
0x18003b068  sub     rcx, 10h
0x18003b06c  call    ??_G?$shared_ptr@VCamera@Engine@Spectre@@@std@@QEAAPEAXI@Z; std::shared_ptr<Spectre::Engine::Camera>::`scalar deleting destructor'(uint)
0x18003b071  add     qword ptr [rdi+180h], 0FFFFFFFFFFFFFFF0h
0x18003b079  cmp     byte ptr [rdi+68h], 0
0x18003b07d  jz      short loc_18003B091
0x18003b07f  mov     rcx, [rbx]
0x18003b082  mov     rax, [rcx]
0x18003b085  mov     rax, [rax+80h]
0x18003b08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b091  mov     rcx, [rbx]
0x18003b094  mov     rax, [rcx]
0x18003b097  mov     rax, [rax+70h]
0x18003b09b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b0a0  nop
0x18003b0a1  mov     rcx, [rbx+8]; this
0x18003b0a5  test    rcx, rcx
0x18003b0a8  jz      short loc_18003B0AF
0x18003b0aa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b0af  mov     rcx, [rsp+0C8h+var_10]
0x18003b0b7  xor     rcx, rsp; StackCookie
0x18003b0ba  call    __security_check_cookie
0x18003b0bf  mov     rbx, [rsp+0C8h+arg_10]
0x18003b0c7  add     rsp, 0C0h
0x18003b0ce  pop     rdi
0x18003b0cf  retn
```
