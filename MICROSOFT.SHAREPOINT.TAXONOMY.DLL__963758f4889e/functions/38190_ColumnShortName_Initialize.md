# ColumnShortName::Initialize

- ea: `0x38190`
- end: `0x38595`
- name: `ColumnShortName::Initialize`
- size: `1029`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x38170`

## string_xrefs

- `0x38205`: `CreatedTime`
- `0x38285`: `IsOpen`
- `0x382f5`: `IsDeleted`
- `0x383c5`: `IdPath`
- `0x38415`: `FullGuidPath`
- `0x38565`: `WssIds`
- `0x38585`: `IsReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x38190  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> ColumnShortName::NameMap
0x38195  ldstr    aPartitionid_1// "PartitionId"
0x3819a  ldstr    aA0// "a0"
0x3819f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x381a4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> ColumnShortName::NameMap
0x381a9  ldstr    aGroupid_1// "GroupId"
0x381ae  ldstr    aA1// "a1"
0x381b3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x381b8  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> ColumnShortName::NameMap
0x381bd  ldstr    aPrincipalname_0// "PrincipalName"
0x381c2  ldstr    aA2// "a2"
0x381c7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x381cc  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> ColumnShortName::NameMap
0x381d1  ldstr    aDisplayname// "DisplayName"
0x381d6  ldstr    aA3// "a3"
0x381db  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x381e0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> ColumnShortName::NameMap
0x381e5  ldstr    aRights// "Rights"
0x381ea  ldstr    aA4// "a4"
0x381ef  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x381f4  ldarg.0
0x381f5  ldstr    aId// "Id"
0x381fa  ldstr    aA6// "a6"
0x381ff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38204  ldarg.0
0x38205  ldstr    aCreatedtime// "CreatedTime"
0x3820a  ldstr    aA7// "a7"
0x3820f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38214  ldarg.0
0x38215  ldstr    aLastmodifiedti_1// "LastModifiedTime"
0x3821a  ldstr    aA8// "a8"
0x3821f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38224  ldarg.0
0x38225  ldstr    aUniqueid// "UniqueId"
0x3822a  ldstr    aA9// "a9"
0x3822f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38234  ldarg.0
0x38235  ldstr    aDescription// "Description"
0x3823a  ldstr    aA11// "a11"
0x3823f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38244  ldarg.0
0x38245  ldstr    aName// "Name"
0x3824a  ldstr    aA12// "a12"
0x3824f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38254  ldarg.0
0x38255  ldstr    aOwner_0// "Owner"
0x3825a  ldstr    aA14// "a14"
0x3825f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38264  ldarg.0
0x38265  ldstr    aCustomsortorde_1// "CustomSortOrder"
0x3826a  ldstr    aA67// "a67"
0x3826f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38274  ldarg.0
0x38275  ldstr    aType// "Type"
0x3827a  ldstr    aA15// "a15"
0x3827f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38284  ldarg.0
0x38285  ldstr    aIsopen// "IsOpen"
0x3828a  ldstr    aA16// "a16"
0x3828f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38294  ldarg.0
0x38295  ldstr    aAvailableforta_0// "AvailableForTagging"
0x3829a  ldstr    aA17// "a17"
0x3829f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x382a4  ldarg.0
0x382a5  ldstr    aStakeholders_0// "Stakeholders"
0x382aa  ldstr    aA18// "a18"
0x382af  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x382b4  ldarg.0
0x382b5  ldstr    aContact// "Contact"
0x382ba  ldstr    aA68// "a68"
0x382bf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x382c4  ldarg.0
0x382c5  ldstr    aLastusedtime// "LastUsedTime"
0x382ca  ldstr    aA19// "a19"
0x382cf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x382d4  ldarg.0
0x382d5  ldstr    aUsecount// "UseCount"
0x382da  ldstr    aA20// "a20"
0x382df  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x382e4  ldarg.0
0x382e5  ldstr    aIsdeprecated// "IsDeprecated"
0x382ea  ldstr    aA21// "a21"
0x382ef  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x382f4  ldarg.0
0x382f5  ldstr    aIsdeleted// "IsDeleted"
0x382fa  ldstr    aA22// "a22"
0x382ff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38304  ldarg.0
0x38305  ldstr    aMergedidlist// "MergedIdList"
0x3830a  ldstr    aA23// "a23"
0x3830f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38314  ldarg.0
0x38315  ldstr    aClientid// "ClientId"
0x3831a  ldstr    aA61// "a61"
0x3831f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38324  ldarg.0
0x38325  ldstr    aTermsetid// "TermSetId"
0x3832a  ldstr    aA24// "a24"
0x3832f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38334  ldarg.0
0x38335  ldstr    aParenttermid_0// "ParentTermId"
0x3833a  ldstr    aA25// "a25"
0x3833f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38344  ldarg.0
0x38345  ldstr    aIssource// "IsSource"
0x3834a  ldstr    aA26// "a26"
0x3834f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38354  ldarg.0
0x38355  ldstr    aIsdefault// "IsDefault"
0x3835a  ldstr    aA31// "a31"
0x3835f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38364  ldarg.0
0x38365  ldstr    aLabel_1// "Label"
0x3836a  ldstr    aA32// "a32"
0x3836f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38374  ldarg.0
0x38375  ldstr    aLcid_0// "LCID"
0x3837a  ldstr    aA33// "a33"
0x3837f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38384  ldarg.0
0x38385  ldstr    aTermid_1// "TermId"
0x3838a  ldstr    aA34// "a34"
0x3838f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38394  ldarg.0
0x38395  ldstr    aIskeyword// "IsKeyword"
0x3839a  ldstr    aA35// "a35"
0x3839f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x383a4  ldarg.0
0x383a5  ldstr    aPropertyname_1// "PropertyName"
0x383aa  ldstr    aA37// "a37"
0x383af  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x383b4  ldarg.0
0x383b5  ldstr    aPropertyvalue_1// "PropertyValue"
0x383ba  ldstr    aA38// "a38"
0x383bf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x383c4  ldarg.0
0x383c5  ldstr    aIdpath// "IdPath"
0x383ca  ldstr    aA39// "a39"
0x383cf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x383d4  ldarg.0
0x383d5  ldstr    aPath// "Path"
0x383da  ldstr    aA40// "a40"
0x383df  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x383e4  ldarg.0
0x383e5  ldstr    aTermsetguid// "TermSetGuid"
0x383ea  ldstr    aA41// "a41"
0x383ef  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x383f4  ldarg.0
0x383f5  ldstr    aTermsetname_0// "TermSetName"
0x383fa  ldstr    aA42// "a42"
0x383ff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38404  ldarg.0
0x38405  ldstr    aParenttermguid// "ParentTermGuid"
0x3840a  ldstr    aA43// "a43"
0x3840f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38414  ldarg.0
0x38415  ldstr    aFullguidpath// "FullGuidPath"
0x3841a  ldstr    aA71// "a71"
0x3841f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38424  ldarg.0
0x38425  ldstr    aGroupuniqueid// "GroupUniqueId"
0x3842a  ldstr    aA48// "a48"
0x3842f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38434  ldarg.0
0x38435  ldstr    aTermsetuniquei// "TermSetUniqueId"
0x3843a  ldstr    aA49// "a49"
0x3843f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38444  ldarg.0
0x38445  ldstr    aObjectuniqueid// "ObjectUniqueId"
0x3844a  ldstr    aA50// "a50"
0x3844f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38454  ldarg.0
0x38455  ldstr    aObjectid_0// "ObjectId"
0x3845a  ldstr    aA51// "a51"
0x3845f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38464  ldarg.0
0x38465  ldstr    aObjecttype// "ObjectType"
0x3846a  ldstr    aA52// "a52"
0x3846f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38474  ldarg.0
0x38475  ldstr    aChangetype_0// "ChangeType"
0x3847a  ldstr    aA53// "a53"
0x3847f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38484  ldarg.0
0x38485  ldstr    aChangetime// "ChangeTime"
0x3848a  ldstr    aA54// "a54"
0x3848f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38494  ldarg.0
0x38495  ldstr    aMaxchangetime// "MaxChangeTime"
0x3849a  ldstr    aA73// "a73"
0x3849f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x384a4  ldarg.0
0x384a5  ldstr    aChangedata// "ChangeData"
0x384aa  ldstr    aA55// "a55"
0x384af  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x384b4  ldarg.0
0x384b5  ldstr    aModifiedby// "ModifiedBy"
0x384ba  ldstr    aA56// "a56"
0x384bf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x384c4  ldarg.0
0x384c5  ldstr    aChildtermid// "ChildTermId"
0x384ca  ldstr    aA57// "a57"
0x384cf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x384d4  ldarg.0
0x384d5  ldstr    aIsdefaultlangu_0// "IsDefaultLanguage"
0x384da  ldstr    aA58// "a58"
0x384df  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x384e4  ldarg.0
0x384e5  ldstr    aWorkinglanguag_0// "WorkingLanguageId"
0x384ea  ldstr    aA59// "a59"
0x384ef  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x384f4  ldarg.0
0x384f5  ldstr    aSiteguid// "SiteGuid"
0x384fa  ldstr    aA60// "a60"
0x384ff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38504  ldarg.0
0x38505  ldstr    aSettings_0// "Settings"
0x3850a  ldstr    aA62// "a62"
0x3850f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38514  ldarg.0
0x38515  ldstr    aSiteurl// "SiteUrl"
0x3851a  ldstr    aA63// "a63"
0x3851f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38524  ldarg.0
0x38525  ldstr    aObjectname_0// "ObjectName"
0x3852a  ldstr    aA64// "a64"
0x3852f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38534  ldarg.0
0x38535  ldstr    aStage_0// "Stage"
0x3853a  ldstr    aA65// "a65"
0x3853f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38544  ldarg.0
0x38545  ldstr    aMessage_0// "Message"
0x3854a  ldstr    aA66// "a66"
0x3854f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38554  ldarg.0
0x38555  ldstr    aIsfirstonly// "IsFirstOnly"
0x3855a  ldstr    aA70// "a70"
0x3855f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38564  ldarg.0
0x38565  ldstr    aWssids// "WssIds"
0x3856a  ldstr    aA1000// "a1000"
0x3856f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38574  ldarg.0
0x38575  ldstr    aPinsourceterms_0// "PinSourceTermSetId"
0x3857a  ldstr    aA74// "a74"
0x3857f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38584  ldarg.0
0x38585  ldstr    aIsreadonly_0// "IsReadOnly"
0x3858a  ldstr    aA72// "a72"
0x3858f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x38594  ret
```
