# CloudExperienceHostLaunchTask::ShowPostponeToast(ushort const *,ulong)

- ea: `0x180015a90`
- end: `0x180015cf8`
- name: `?ShowPostponeToast@CloudExperienceHostLaunchTask@@AEAAXPEBGK@Z`
- size: `616`
- prototype: `void __fastcall(CloudExperienceHostLaunchTask *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011538`

## callees

- `0x18000a5c8`
- `0x18000aab8`
- `0x18000e2bc`
- `0x18000e580`
- `0x180010c28`
- `0x180010dc8`
- `0x180012ab8`
- `0x180015a90`
- `0x180015d00`
- `0x18002d630`

## string_xrefs

- `0x180015adb`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180015b1e`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180015ba0`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180015c0b`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180015b5e`: `<toast scenario="reminder" launch="activateToast?params={&quot;URI&quot; : &quot;%ws&quot;, &quot;PreviousNumberOfConsecutivePostpones&quot; : %u}"><visual> <binding template="ToastGeneric"><text>%ws</text> <text hint-style="captionsubtle">%ws</text> %ws </binding> </visual><actions>`
- `0x180015bc1`: `<action arguments="activateToast?params={&quot;URI&quot; : &quot;%ws&quot;, &quot;PreviousNumberOfConsecutivePostpones&quot; : %u}" content="%ws" />`
- `0x180015c34`: `<action arguments="activateToast?params={&quot;URI&quot; : &quot;%ws&quot;, &quot;PreviousNumberOfConsecutivePostpones&quot; : %u, &quot;NumMinutesToPostpone&quot; : %d}" content="%ws" />`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CloudExperienceHostLaunchTask::ShowPostponeToast(
        CloudExperienceHostLaunchTask *this,
        const unsigned __int16 *a2,
        unsigned int a3)
{
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  int v9; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int v13; // eax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v17; // eax
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  const unsigned __int16 *v24; // rdx
  CloudExperienceHostLaunchTask *v25; // rcx
  int v26; // [rsp+20h] [rbp-39h]
  int v27; // [rsp+20h] [rbp-39h]
  int v28[2]; // [rsp+20h] [rbp-39h]
  int v29[2]; // [rsp+40h] [rbp-19h] BYREF
  unsigned __int16 *v30; // [rsp+48h] [rbp-11h] BYREF
  __int64 v31; // [rsp+50h] [rbp-9h] BYREF
  int v32[2]; // [rsp+58h] [rbp-1h] BYREF
  __int64 v33; // [rsp+60h] [rbp+7h] BYREF
  __int64 v34; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v35; // [rsp+70h] [rbp+17h] BYREF
  __int64 v36; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v37; // [rsp+80h] [rbp+27h] BYREF
  _BYTE v38[40]; // [rsp+88h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  __int64 v40; // [rsp+D8h] [rbp+7Fh] BYREF

  *(_QWORD *)v32 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v32,
    0);
  v9 = TResourceStringAllocCopyEx<unsigned short *>(v6, 1108, v7, v8);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)v9,
      v26);
  v31 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v31,
    0);
  v13 = TResourceStringAllocCopyEx<unsigned short *>(v10, 1109, v11, v12);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)v13,
      v26);
  CloudExperienceHostLaunchTask::GenerateImageContent(this, &v36);
  v27 = v32[0];
  wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v30,
    L"<toast scenario=\"reminder\" launch=\"activateToast?params={&quot;URI&quot; : &quot;%ws&quot;, &quot;PreviousNumberO"
     "fConsecutivePostpones&quot; : %u}\"><visual> <binding template=\"ToastGeneric\"><text>%ws</text> <text hint-style=\""
     "captionsubtle\">%ws</text> %ws </binding> </visual><actions>",
    a2,
    a3);
  *(_QWORD *)v29 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v29,
    0);
  v17 = TResourceStringAllocCopyEx<unsigned short *>(v14, 1000, v15, v16);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x124,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)v17,
      v27);
  *(_QWORD *)v28 = *(_QWORD *)v29;
  wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v35,
    L"<action arguments=\"activateToast?params={&quot;URI&quot; : &quot;%ws&quot;, &quot;PreviousNumberOfConsecutivePostpo"
     "nes&quot; : %u}\" content=\"%ws\" />",
    a2,
    a3);
  v33 = 0;
  v40 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v40,
    0);
  v21 = TResourceStringAllocCopyEx<unsigned short *>(v18, 1001, v19, v20);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)v21,
      v28[0]);
  v28[0] = -1;
  v22 = wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v34,
          L"<action arguments=\"activateToast?params={&quot;URI&quot; : &quot;%ws&quot;, &quot;PreviousNumberOfConsecutive"
           "Postpones&quot; : %u, &quot;NumMinutesToPostpone&quot; : %d}\" content=\"%ws\" />",
          a2,
          a3,
          *(_QWORD *)v28,
          v40);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &v33,
    v22);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v34);
  v34 = v33;
  v37 = v35;
  v23 = wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>> &,unsigned short *,unsigned short *,unsigned short const (&)[12],unsigned short const (&)[9]>(
          v38,
          &v30,
          &v37,
          &v34);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &v30,
    v23);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v38);
  CloudExperienceHostLaunchTask::ShowToastNotificationFromXml(v25, v24, v30);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v40);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v33);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v35);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v29);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v30);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v36);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v31);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v32);
}

```

## disassembly

```asm
0x180015a90  push    rbp
0x180015a92  push    rbx
0x180015a93  push    rsi
0x180015a94  push    rdi
0x180015a95  lea     rbp, [rsp-3Fh]
0x180015a9a  sub     rsp, 98h
0x180015aa1  mov     ebx, r8d
0x180015aa4  mov     rdi, rdx
0x180015aa7  mov     rsi, rcx
0x180015aaa  mov     qword ptr [rbp+57h+var_58], 0
0x180015ab2  xor     edx, edx
0x180015ab4  lea     rcx, [rbp+57h+var_58]
0x180015ab8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015abd  lea     rax, [rbp+57h+var_58]
0x180015ac1  mov     [rsp+0B0h+var_88], rax
0x180015ac6  mov     edx, 454h
0x180015acb  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180015ad0  mov     rcx, [rbp+5Fh]; this
0x180015ad4  test    eax, eax
0x180015ad6  jns     short loc_180015AED
0x180015ad8  mov     r9d, eax; char *
0x180015adb  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180015ae2  mov     edx, 117h; void *
0x180015ae7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015aed  mov     [rbp+57h+var_60], 0
0x180015af5  xor     edx, edx
0x180015af7  lea     rcx, [rbp+57h+var_60]
0x180015afb  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015b00  lea     rax, [rbp+57h+var_60]
0x180015b04  mov     [rsp+0B0h+var_88], rax
0x180015b09  mov     edx, 455h
0x180015b0e  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180015b13  mov     rcx, [rbp+5Fh]; this
0x180015b17  test    eax, eax
0x180015b19  jns     short loc_180015B30
0x180015b1b  mov     r9d, eax; char *
0x180015b1e  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180015b25  mov     edx, 119h; void *
0x180015b2a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015b30  lea     rdx, [rbp+57h+var_38]
0x180015b34  mov     rcx, rsi
0x180015b37  call    ?GenerateImageContent@CloudExperienceHostLaunchTask@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; CloudExperienceHostLaunchTask::GenerateImageContent(void)
0x180015b3c  nop
0x180015b3d  mov     rax, [rbp+57h+var_38]
0x180015b41  mov     [rsp+0B0h+var_80], rax
0x180015b46  mov     rax, [rbp+57h+var_60]
0x180015b4a  mov     [rsp+0B0h+var_88], rax
0x180015b4f  mov     rax, qword ptr [rbp+57h+var_58]
0x180015b53  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x180015b58  mov     r9d, ebx
0x180015b5b  mov     r8, rdi
0x180015b5e  lea     rdx, aToastScenarioR; "<toast scenario=\"reminder\" launch=\"a"...
0x180015b65  lea     rcx, [rbp+57h+var_68]
0x180015b69  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x180015b6e  nop
0x180015b6f  mov     qword ptr [rbp+57h+var_70], 0
0x180015b77  xor     edx, edx
0x180015b79  lea     rcx, [rbp+57h+var_70]
0x180015b7d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015b82  lea     rax, [rbp+57h+var_70]
0x180015b86  mov     [rsp+0B0h+var_88], rax
0x180015b8b  mov     edx, 3E8h
0x180015b90  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180015b95  mov     rcx, [rbp+5Fh]; this
0x180015b99  test    eax, eax
0x180015b9b  jns     short loc_180015BB2
0x180015b9d  mov     r9d, eax; char *
0x180015ba0  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180015ba7  mov     edx, 124h; void *
0x180015bac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015bb2  mov     rax, qword ptr [rbp+57h+var_70]
0x180015bb6  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x180015bbb  mov     r9d, ebx
0x180015bbe  mov     r8, rdi
0x180015bc1  lea     rdx, aActionArgument_0; "<action arguments=\"activateToast?param"...
0x180015bc8  lea     rcx, [rbp+57h+var_40]
0x180015bcc  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x180015bd1  nop
0x180015bd2  mov     [rbp+57h+var_50], 0
0x180015bda  mov     [rbp+57h+arg_18], 0
0x180015be2  xor     edx, edx
0x180015be4  lea     rcx, [rbp+57h+arg_18]
0x180015be8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015bed  lea     rax, [rbp+57h+arg_18]
0x180015bf1  mov     [rsp+0B0h+var_88], rax
0x180015bf6  mov     edx, 3E9h
0x180015bfb  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180015c00  mov     rcx, [rbp+5Fh]; this
0x180015c04  test    eax, eax
0x180015c06  jns     short loc_180015C1D
0x180015c08  mov     r9d, eax; char *
0x180015c0b  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180015c12  mov     edx, 12Dh; void *
0x180015c17  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015c1d  mov     rax, [rbp+57h+arg_18]
0x180015c21  mov     [rsp+0B0h+var_88], rax
0x180015c26  mov     [rsp+0B0h+var_90], 0FFFFFFFFh
0x180015c2e  mov     r9d, ebx
0x180015c31  mov     r8, rdi
0x180015c34  lea     rdx, aActionArgument; "<action arguments=\"activateToast?param"...
0x180015c3b  lea     rcx, [rbp+57h+var_48]
0x180015c3f  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x180015c44  mov     rdx, rax
0x180015c47  lea     rcx, [rbp+57h+var_50]
0x180015c4b  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180015c50  lea     rcx, [rbp+57h+var_48]
0x180015c54  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180015c59  mov     rax, [rbp+57h+var_50]
0x180015c5d  mov     [rbp+57h+var_48], rax
0x180015c61  mov     rax, [rbp+57h+var_40]
0x180015c65  mov     [rbp+57h+var_30], rax
0x180015c69  lea     r9, [rbp+57h+var_48]
0x180015c6d  lea     r8, [rbp+57h+var_30]
0x180015c71  lea     rdx, [rbp+57h+var_68]
0x180015c75  lea     rcx, [rbp+57h+var_28]
0x180015c79  call    ??$str_concat@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV12@PEAGPEAGAEAY0M@$$CBGAEAY08$$CBG@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAV10@$$QEAPEAG1AEAY0M@$$CBGAEAY08$$CBG@Z; wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort *,ushort *,ushort const (&)[12],ushort const (&)[9]>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort * &&,ushort * &&,ushort const (&)[12],ushort const (&)[9])
0x180015c7e  mov     rdx, rax
0x180015c81  lea     rcx, [rbp+57h+var_68]
0x180015c85  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180015c8a  lea     rcx, [rbp+57h+var_28]
0x180015c8e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180015c93  mov     r8, [rbp+57h+var_68]; unsigned __int16 *
0x180015c97  call    ?ShowToastNotificationFromXml@CloudExperienceHostLaunchTask@@AEAAXPEBG0@Z; CloudExperienceHostLaunchTask::ShowToastNotificationFromXml(ushort const *,ushort const *)
0x180015c9c  nop
0x180015c9d  lea     rcx, [rbp+57h+arg_18]
0x180015ca1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180015ca6  nop
0x180015ca7  lea     rcx, [rbp+57h+var_50]
0x180015cab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180015cb0  nop
0x180015cb1  lea     rcx, [rbp+57h+var_40]
0x180015cb5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180015cba  nop
0x180015cbb  lea     rcx, [rbp+57h+var_70]
0x180015cbf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180015cc4  nop
0x180015cc5  lea     rcx, [rbp+57h+var_68]
0x180015cc9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180015cce  nop
0x180015ccf  lea     rcx, [rbp+57h+var_38]
0x180015cd3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180015cd8  nop
0x180015cd9  lea     rcx, [rbp+57h+var_60]
0x180015cdd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180015ce2  nop
0x180015ce3  lea     rcx, [rbp+57h+var_58]
0x180015ce7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180015cec  add     rsp, 98h
0x180015cf3  pop     rdi
0x180015cf4  pop     rsi
0x180015cf5  pop     rbx
0x180015cf6  pop     rbp
0x180015cf7  retn
```
